+++
title = "stringless"
date = 2017-06-13
updated = 2021-03-01

[taxonomies]
categories = ["software"]

[extra]
featured_image = "img.png"
repo_path = "justint/stringless"
+++
Real-time single-camera markerless facial motion capture into Autodesk Maya.
<!-- more -->

[Stringless](https://github.com/justint/stringless/) is a proof-of-concept real time, single camera, markerless facial motion capture system. It includes a plugin for sending motion capture data to Autodesk Maya, and was built to be extendable to other animation software. I developed it as my thesis project for my CS undergraduate degree at San Jose State University in 2017.

By using [dlib](http://dlib.net/) facial landmark detection, Stringless captures facial motion data as a collection of data points. That data is sent to an Autodesk Maya plug-in, where a user can map the motion capture data to a rigged face model.

&nbsp;

![Demonstration GIF of Stringless in use](https://github.com/justint/stringless/raw/main/stringless.gif)

<p style="text-align: center; font-weight: bold"><a href="https://github.com/justint/stringless/">View on GitHub</a> ◦ <a href="https://justintennant.me/Stringless_NASA_Presentation.pdf">Presentation</a></p>

Stringless is a prototype of a motion capture system intended for casual/non-professional animators and visual development ("visdev"). Practically any user with a webcam and a modern computer processor (supporting AVX[^1] or SSE4 instruction sets) can utilize Stringless.

# Why build Stringless?

Upon entering my final year at San Jose State University, I was eager to flex my skills in C++ and craft my thesis project within the computer graphics and computer vision space. My mentor and computer graphics course instructor Robert Bruce advised I consider pursuing a project relating to facial motion capture. 

[Facial motion capture](https://en.wikipedia.org/wiki/Facial_motion_capture) is a complicated problem space; depending on a system's criteria of capturing methodologies, the resulting capture data's dimensional depth, quality, and stability can vary greatly:

| Markered | Markerless |
| -------- | ---------- |
| <ul><li>Excellent capture quality</li><li>Meticulous setup required</li></ul> | <ul><li>Potentially unstable tracking</li><li>Minimal setup required</li></ul> | 

&nbsp;

| Multi-camera | Single-camera |
| -------- | ---------- |
| <ul><li>Three-dimensional capture data</li><li>Costly</li></ul> | <ul><li>Two-dimensional capture data</li><li>Less costly</li></ul> | 

&nbsp;

| Realtime | Offline |
| -------- | ---------- |
| <ul><li>Immediate results</li><li>Potentially computationally expensive</li></ul> | <ul><li>Delayed results</li><li>Potentially laborious data processing</li></ul> | 

At the time of my final year at San Jose State University, most quality facial motion capture systems existed as internal, proprietary software, developed and utilized within their respective Visual Effects and Computer Graphics companies. The remaining options available for licensing had either extensive hardware/recording requirements (multi-camera setups, additional infrared projectors, or markers) or prohibitively expensive costs. 

These options seemed inaccessible to individuals without large budgets like students, non-professional artists, or small independent studios. A low-cost, low-hardware requirement facial motion capture system didn't seem to exist.

Recognizing this unsolved space, I decided to attempt a prototype of a facial motion capture system that addressed all the facets of the problem:

- _Markers are cumbersome_.

- _Multi-camera setups are expensive_.
  
- _Ingesting capture data can be laborious_. 

With these factors in mind, I designed and built a facial motion capture system prototype (now known as Stringless) that would be:

 - **markerless**, requiring no markers on the actor's face for capturing,
   
 - **single-camera**, averting the need for expensive equipment, and

 - **real-time**, allowing the capture results to be immediately viewed.

By avoiding the costly addition of multiple cameras and laborious work of using markers, Stringless can be used by practically anyone with a computer and a webcam.

# How it works

Stringless operates with an IPC client-server model: **the server** collects the image frames from the webcam and processes them using the dlib machine learning toolkit to generate facial landmark positions; **the client** then reads in the landmark position data which the user can link to the 3D rig joints.

{{ img(path="@/projects/stringless/architecture.png", extended_width_pct=0.2, alt="Stringless system architecture diagram.", caption="Stringless system architecture diagram.") }}

Stringless's architecture was built with extensibility in mind by implementing its client-server model over POSIX shared memory. This allows Stringless to send data not only to Autodesk Maya, but potentially any other 3D application that can implement the Stringless Reader interface. 

Here's a related thread on how one could theoretically extend usage outside of Maya: [_Using Blender instead of Maya (#9) · justint/stringless_](https://github.com/justint/stringless/issues/9)

Stringless also uses **localized delta calculations** to produce the outputted positional data -- the user defines a neutral face definition using the server application UI, then the resulting localized face is defined by the deltas from the neutral face. Three-dimensional rotations (pitch, yaw, and roll) are not yet accounted for; see [my later note](#results) on the recorded data being two-dimensional.

# Results

The Stringless system is fully functional; it can pipe two-dimensional data (68 2D facial landmark points) using localized delta calculations to drive a rig in Autodesk Maya.

Below is a chart of resolution-to-framerate performance metrics, recorded on an Intel Core i9-7960X with a Logitech BRIO webcam:

| Capture resolution | Frames per second (avg) |
| ------------------ | ----------------------- |
| 4k                 | 26                      |
| 1920x1080          | 60                      |
| 1280x720           | 90                      |
| 640x480            | 120                     |

Due to certain design choices within the system, some caveats to its operation exist:

- **Using a single camera means the recorded data is two-dimensional** -- the 68 facial landmarks that dlib generates when locating faces are processed & recorded in 2D space only. Ultimately we'd want to have some abstracted layer above the raw 2D data that provides three-dimensional data, like rotation values of the head and per-facial feature data (e.g.: eye/mouth open/close amounts, eyebrow raise amounts, etc.). This could certainly be doable with enough matrix & vector mathematics, but I haven't had the will or time to implement it.

- **Stringless can only operate on POSIX shared memory compatible systems** -- this essentially means macOS and Linux only, for now. If the desire is strong enough to eventually get Stringless working on Windows, we could rewrite its client-server system to an OS-independent IPC method like socket communication.

There are also some known issues:

 - Lighting conditions must be decent to ensure face identifications
 - Potential face identification failures from facial expressions/gaze being too distant from the training data
 - A consistent face direction is required during capture due to the localized delta calculation system

# Future thoughts

New development from me has ceased since my graduating, with only occasional maintenance and code repository cleaning. After finishing development in 2017 I dumped a backlog of nice-to-have features onto the repository's issues; here are a select few worth noting:

- Cross-platform support ([justint/stringless#4](https://github.com/justint/stringless/issues/4))
- Implement eye tracking ([justint/stringless#5](https://github.com/justint/stringless/issues/5))
- Process & provide three-dimensional rotation, per-facial feature data ([justint/stringless#7](https://github.com/justint/stringless/issues/7))
- Integration with other animation software (Blender: [justint/stringless#9](https://github.com/justint/stringless/issues/7))

[^1]: Most Intel/AMD processors released after 2013 support AVX instructions: [https://en.wikipedia.org/wiki/Advanced_Vector_Extensions#CPUs_with_AVX](https://en.wikipedia.org/wiki/Advanced_Vector_Extensions#CPUs_with_AVX).