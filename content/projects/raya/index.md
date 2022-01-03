+++
title = "Raya and the Last Dragon"
date = 2021-03-05

[taxonomies]
categories = ["film"]

[extra]
featured_image = "img.jpg"
featured_image_alt = "Raya and Namaari face off in a scene from Raya and the Last Dragon"
featured_image_extended = true
+++
Walt Disney Animation Studios feature film -- worked on lighting & volume pipelines as a Technical Director.
<!-- more -->

_Raya and the Last Dragon_ is the second film at Walt Disney Animation Studios I've had the privilege of working on (and one of my favorites stylistically!). 

[comment]: <> (I remember seeing the early concept art of the &#40;insert snowy world name here - spine? tail?&#41; world during my first few days at the studio and being stunned by the beauty and potential. The world was so thrilling, alive, and magical - I remember the strong forced perspective of the trees & buildings. Seeing those early on, I had asked my artist manager way ahead of my casting time to be put on the show.)

[comment]: <> (_Raya_ was a difficult film to make, given the challenges of the COVID pandemic. A majority of the production was done from home, myself included.  )

# My Contributions to the Film 

On _Raya_ I worked as a Technical Director, performing a mixture of **scripting, tools development, and problem solving for our artists & their workflows**. 

For this show specifically, my focus was in developing & supporting the Lighting department. One of my most significant contributions to the production was the development of our volumetrics pipeline, which allowed our lighting artists to place clouds, fog, mist, and other volumetric assets directly into their shots. This significantly lowered the need for expensive, per-shot Effects-produced volumetrics. The pipeline also supported a multi-shot workflow, allowing our lighting supervisors to insert multiple volumes across a range of shots in any one sequence.[^1] 

Below are a few examples of how the volumetrics affected the look of the film.

_Use the slider to preview the before and after of adding volumetrics into these shots:_

{{ slider(id="1", before_path="@/projects/raya/1_before_volumes.jpg", after_path="@/projects/raya/1_after_volumes.jpg", extended_width_pct=0.5 ) }}

&nbsp;

{{ slider(id="2", before_path="@/projects/raya/2_before_volumes.jpg", after_path="@/projects/raya/2_after_volumes.jpg", extended_width_pct=0.5) }}

&nbsp;

{{ slider(id="3", before_path="@/projects/raya/3_before_volumes.jpg", after_path="@/projects/raya/3_after_volumes.jpg", extended_width_pct=0.5) }}

_Images courtesy of and the property of Walt Disney Animation Studios._

The volumetrics pipeline was a collaborative effort between multiple departments: the _effects team_ procured the volumes to be placed into our stockroom, the _Hyperion rendering team_ implemented new technology to render the complex heterogenerous volumes (more details in Karl Li's [excellent blog post](https://blog.yiningkarlli.com/2021/03/raya-and-the-last-dragon.html)), the _preview rendering team_ to ensure the volumes displayed beautifully in our artists' tools, and the _technical director team_ (that's me!) developed the neccessary additions to our production pipeline to support our lighting artists adding the volumes into the shots.

My contributions focused on those additions to our existing production pipeline - I lead the development of a **new data extraction & organization methodology** and **authoring GUI tool** for these volumetrics. 

This new methodology defined how the local lighting artists' volumetric data should be extracted from their scenes and made available in the target destination shots. It also provided the ability for our lighting supervisors to bring in volumes and work in a multi-shot context within one DCC editing instance, and publish out those volumes across multiple shots with one action. All of this functionality was made available through a new user interface accessible to our artists directly.

# Documenting our Filmmaking Process 

Our studio has curated a website to illustrate how our films are made. It's very pretty and fun to explore - [go check it out](https://disneyanimation.com/process/)!

{{ img(path="@/projects/raya/process.png", extended_width_pct=0.2, alt="What We Do: Filmmaking Process - Walt Disney Animation Studios", caption="What We Do: the Filmmaking Process from the <a href='https://disneyanimation.com/process/'>Walt Disney Animation Studios website</a>.") }}

[^1]: Marc Bryant, Ryan DeYoung, Wei-Feng Wayne Huang, Joe Longson, and Noel Villegas. 2021. _The Atmosphere of Raya and the Last Dragon_. In ACM SIGGRAPH 2021 Talks (_SIGGRAPH '21_). Association for Computing Machinery, New York, NY, USA, Article 51, 1–2. DOI: 
[https://dl.acm.org/doi/abs/10.1145/3450623.3464676](https://dl.acm.org/doi/abs/10.1145/3450623.3464676)