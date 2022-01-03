+++
title = "Frozen 2"
date = 2019-11-07

[taxonomies]
categories = ["film"]

[extra]
featured_image = "img.jpg"
featured_image_alt = "Frozen 2 - Elsa and Anna walking into the Unknown"
featured_image_extended = true
+++
Walt Disney Animation Studios feature film -- worked on crowds pipeline, support & bug fixing, and more as an Assistant Technical Director.
<!-- more -->

_Frozen 2_ is the first feature film I've had the privilege to work on, and I am immensely proud of what our crew accomplished to produce this stunning visual magic.

On _Frozen 2_ I worked as an Assistant Technical Director, performing a mixture of scripting, tools development, and problem solving for our artists & their workflows. As a member of the Technical Director department, I represented  the intermediate between our artists and software engineers, working as a "steward of the pipeline" to ensure our artists could accomplish their artistic visions with the technology we craft them.

[comment]: <> (Take a look at the teaser trailer below:)

[comment]: <> ({{ youtube&#40;id="eSLe4HuKuK0", class="youtube"&#41; }})

[comment]: <> (Released on February 13, 2019, the trailer accumulated 116.4 million views globally its first 24 hours, setting the record of the most-viewed animated trailer release ever. Talk about an anticipated film!)

## Background

A little context about how I got to work on _Frozen 2_:

I joined Walt Disney Animation Studios through their Talent Development Program as a Technical Director Trainee in 2018[^1]. After 3 months as a trainee, I was cast to Frozen 2 as an Assistant Technical Director and assisted nearly all the production departments on producing and rendering this film. 

Besides it being my first film to work on at Walt Disney Animation Studios and my first credit, _Frozen 2_ holds a particularly special place in my heart for another reason: the first _Frozen_ movie motivated me to enter the computer graphics industry. Specifically, the _A Material Point Method for Snow Simulation_[^2] publication from the film's technical development was a defining point of inspiration during my years as a college student. To have worked on its direct sequel, at the studio that produced it, is a true honor and a highlight of my career.

{{ img(path="@/projects/frozen2/teaser.jpg", extended_width_pct=0.2, alt="Frozen 2 - Teaser shot", caption="The gang overlook the enchanted forest. From the <a href='https://www.youtube.com/watch?v=eSLe4HuKuK0'><i>Frozen 2</i> Official Teaser Trailer</a>.") }}

But enough gushing! Here's a glance at some of the stuff I worked on for this production:

## Crowds (and their luscious locks)

_Frozen 2_ had a lot of crowd characters, and all of them needed to appear presentable -- groomed hair, fitted clothes, the works! Ensuring the best tailored look across all the crowd body types and head shapes was a necessity.

To accomplish this, we used a refitting process that propagated data along our crowd asset hierarchies (described in Luceno Ros et al. 2021, p. 2[^3]). I worked on the part of that process that refit the crowd characters' hair grooms to different head shapes.

{{ img(path="@/projects/frozen2/crowds2.jpg", extended_width_pct=0.2, alt="Frozen 2 - Crowds") }}

{{ img(path="@/projects/frozen2/crowds.jpg", extended_width_pct=0.2, alt="Frozen 2 - Crowds", caption="Some examples of the crowds pipeline in action. Look at that beautifully groomed crowd hair! From a <a href='https://www.youtube.com/watch?v=JntesK7rdTA'><i>Frozen 2</i> trailer</a>.") }}

## Bug fixing & production support

No film ever completes production without some occurrence of technical challenges. 

Part of my responsibility on the show was triaging the many issues that arose from artists: Elsa's hair blowing up, disappearing props and sets, crazy render times, you name it! As an Assistant Technical Director (ATD), the expectation was for me to pick up any issue from any production department and do my best to solve it. 

I also had a hand in touching a number of software products and artist tools for bugfixes that came up during production.


## Optimizations

The Technical Director teams also share a responsibility of optimizing our shots when needed to get them through the pipeline. Below are a few behind-the-scenes highlights of shots I had a hand in optimizing:

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">To create the mist at the entrance to the Enchanted Forest, the Effects team first draped a cloth simulation across the scene. The team populated the cloth simulation with thousands of smaller fluid simulations to build movement. <a href="https://twitter.com/hashtag/TechTuesday?src=hash&amp;ref_src=twsrc%5Etfw">#TechTuesday</a> <a href="https://twitter.com/hashtag/Frozen2?src=hash&amp;ref_src=twsrc%5Etfw">#Frozen2</a> <a href="https://t.co/EwSiB45Cr7">pic.twitter.com/EwSiB45Cr7</a></p>&mdash; Disney Animation (@DisneyAnimation) <a href="https://twitter.com/DisneyAnimation/status/1219771926228303872?ref_src=twsrc%5Etfw">January 22, 2020</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Watch how the Lighting and Look Development artists transformed Ahtohallan with their work in <a href="https://twitter.com/hashtag/Frozen2?src=hash&amp;ref_src=twsrc%5Etfw">#Frozen2</a>. <a href="https://t.co/rWJG8K9jHM">pic.twitter.com/rWJG8K9jHM</a></p>&mdash; Disney Animation (@DisneyAnimation) <a href="https://twitter.com/DisneyAnimation/status/1283151786283601920?ref_src=twsrc%5Etfw">July 14, 2020</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

[comment]: <> (## Crew shirt)

[comment]: <> (Perhaps my greatest artistic creation & contribution to our show was the creation of our department's crew t-shirt. )

[comment]: <> (https://twitter.com/joabaldwin/status/921056585966694400)

[comment]: <> (As part of a regular )

[comment]: <> ({{ img&#40;path="@/projects/frozen2/tshirt.jpg", alt="Frozen 2 Technical Director T-Shirt"&#41; }})

# Related publications

Along with the beautiful artistry crafted for this film, our technical teams went all out to refine our tools and workflows. Here are some publications released by our studio that illustrate the awesome partnerships of art and science on _Frozen 2_:

- **[_Frozen 2_: Effects Vegetation Pipeline](https://disneyanimation.com/publications/frozen-2-effects-vegetation-pipeline/)** -- Norman Moses Joseph, Vijoy Gaddipati, Benjamin Fiske, Marie Tollec, and Tad Miller. 2020. In [_ACM SIGGRAPH 2020 Talks_ (_SIGGRAPH '20_). Article 7, 1–2](https://doi.org/10.1145/3388767.3409320).

- **[Frozen 2: Creating the Wind Spirit](https://www.disneyanimation.com/publications/creating-the-wind-spirit/)** -- Cameron Black, Ben Fiske, and Trent Correy. 2020. In [_ACM SIGGRAPH 2020 Talks_ (_SIGGRAPH '20_). Article 22, 1–2](https://doi.org/10.1145/3388767.3407346).

- **[Making Beautiful Embroidery for _Frozen 2_](https://www.disneyanimation.com/publications/making-beautiful-embroidery-for-frozen-2/)** -- Ying Liu, Jared Wright, and Alexander Alvarado. 2020. In [_ACM SIGGRAPH 2020 Talks_ (_SIGGRAPH '20_). Article 73, 1–2](https://doi.org/10.1145/3388767.3407360).

- **[Deconstructing Destruction: Making & Breaking _Frozen 2_'s Dam](https://www.disneyanimation.com/publications/deconstructing-destruction-making--breaking-frozen-2s-dam/)** -- Marie Tollec, Sean Jenkins, Lance Summers, and Charles Cunningham-Scott. 2020. In [_ACM SIGGRAPH 2020 Talks_ (_SIGGRAPH '20_). Article 24, 1–2](https://doi.org/10.1145/3388767.3407333).

- **[The Look and Lighting of "Show Yourself" from _Frozen 2_](https://www.disneyanimation.com/publications/the-look-and-lighting-of-show-yourself-from-frozen-2/)** -- Amol Sathe, Lance Summers, Matt Jen-Yuan Chiang, and James Newland. 2020. In [_ACM SIGGRAPH 2020 Talks_ (_SIGGRAPH '20_). Article 71, 1–2](https://doi.org/10.1145/3388767.3407388).


[comment]: <> ({{ img&#40;path="@/projects/frozen2/nokk.jpg", extended_width_pct=0.2, alt="Frozen 2 - Elsa and the Nokk", caption="Elsa faces the Nokk, one of four elemental spirits featured in the film. From the <a href='https://www.youtube.com/watch?v=Zi4LMpSDccc'><i>Frozen 2</i> Official Trailer</a>."&#41; }})


[comment]: <> (# Final words)

[comment]: <> (In my first few months at Disney Animation, a coworker told me &#40;slightly paraphrased&#41;: )

[comment]: <> (> "Once you work on a film and see it in its incomplete form, you can never watch it for the first time again". )

[comment]: <> (The meaning became more true to me when I finally watched the film in its final form, at the wrap party. As the film rolled before the crew, here and there I could spot the many shots I worked on, and memories flooded my mind on the hundreds of hours of work spent crafting these images. It was surreal to see one two-second shot go by, knowing those 48 frames were the bane of my existence for a month because of a peculiar issue in rendering. Or spotting certain crowd characters and getting a rush knowing I actually touched that asset!)

[comment]: <> (Some people at the studio intentionally avoid viewing any in-progress work of productions they're not cast to, knowing it'll spoil their viewing of the film later on. I certainly understand their reasoning.)

{{ img(path="@/projects/frozen2/credits.jpg", extended_width_pct=0.2, alt="Frozen 2 credits", caption="Hey, it's me! This is my first film credit.") }}

All images in this post are courtesy of and the property of Walt Disney Animation Studios.

# References

[^1]: The [Trainee & Apprentice Program](https://www.disneyanimation.com/talent-development/apprenticeships/) at Walt Disney Animation Studios is a 9-to-18 month mentored training program for recently graduated/early career artists and technologists. If you're interested in this opportunity, I recommend checking out "Open Positions" on [Disney Animation Careers](https://www.disneyanimation.com/careers/) and look for "Talent Development" roles for your focus of interest.

[^2]: Alexey Stomakhin, Craig Schroeder, Lawrence Chai, Joseph Teran, and Andrew Selle. 2013. [A material point method for snow simulation](https://doi.org/10.1145/2461912.2461948). <i>ACM Trans. Graph.</i> 32, 4, Article 102 (July 2013), 10 pages. [disneyanimation.com](https://www.disneyanimation.com/publications/a-material-point-method-for-snow-simulation/)

[^3]: Alberto Luceno Ros, Kristin Chow, Jack Geckler, Norman Moses Joseph, and Nicolas Nghiem. 2021. [Populating the World of Kumandra: Animation at Scale for Disney’s “Raya and the Last Dragon”](https://doi.org/10.1145/3450623.3464648). In _ACM SIGGRAPH 2021 Talks_ (_SIGGRAPH '21_).  Article 39, 1–2.