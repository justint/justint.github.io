+++
title = "papaya"
date = 2021-08-14

[taxonomies]
categories = ["software"]

[extra]
featured_image = "preview.png"
repo_path = "justint/papaya"
+++
A Zola theme for blogging and projects (what this website runs on!)
<!-- more -->

[comment]: <> (Featured image generated with screely.com)

[papaya](https://github.com/justint/papaya) is a theme I developed for [Zola](https://www.getzola.org/), the static site generator I use to build my website.

Here are some of its features:

- Blog posts
- Project pages
- Categories and tags
- Featured images for posts/pages
- Smart image embedding shortcode (`img()`)
- GitHub repository star/fork counts
- [Open Graph Protocol](https://ogp.me/) tags
- Social/contact links 
- 100% Google Lighthouse score

# Where

The theme is on display in the [Zola themes gallery](https://www.getzola.org/themes/), and its source code is available on [GitHub](https://github.com/justint/papaya) (MIT license). 

To install, follow the [Installation](https://github.com/justint/papaya#installation) steps in the README.

# Why

[comment]: <> (&#40;[why Zola, you ask?]&#40;@/blog/why-zola.md&#41;&#41;)

Back in early 2021, I first began rebuilding my website with Zola using the [Anpu theme](https://www.getzola.org/themes/anpu/). I liked the clean and minimal aesthetics it provided, leaving out the fluff and putting the content first. 

A few months into customizing the theme to my liking, I realized I'd changed a lot of Anpu's core structure to support my desire to showcase my projects. I'd also added a bunch of new features on top of tweaking a significant amount of the theme's styling too.

At some point I figured my changes were enough to warrant a whole fork, and thus [papaya](https://github.com/justint/papaya) was born!

## Core principles

TODO: gotta fill this out eventually :) 

[comment]: <> (### Form)

# How

Creating themes for Zola is [really simple](https://www.getzola.org/documentation/themes/creating-a-theme/) - all you need to do is build a website and add the `theme.toml` file.

During development of my website, I discovered quite a few inspirational tidbits on the internet that drove my final feature list and design aesthetics: 

- **[The Lunaria color palette](https://lunaria.design/)**: algorithmically generated to replicate the ink-on-paper experience on a screen as best as possible. For a while I considered using this palette to style papaya's post content, but instead went with a simpler "black & white with signature color highlights" color palette. 

  I was however heavily inspired by Lunaria's strongly purpose-driven design; for many of papaya's design choices I tried to derive a particular reason and purpose for the decisions I made. I may return to this palette at a later date and try building a Lunaria-based Zola code highlighting theme.

- **[mwaskom.github.io](https://mwaskom.github.io/)**: Michael Waskom's (creator of [seaborn](https://seaborn.pydata.org/)) website.

- **[khyperia.com](https://khyperia.com/)**: khy's simple, clean, and charming personal website. 

- **[Code & Visuals](https://www.yiningkarlli.com/)**: Karl Li's (senior software engineer of Walt Disney Animation Studios' [Hyperion](https://www.disneyanimation.com/technology/hyperion) renderer) quality content-rich website and blog. 

- **[web.dev](https://web.dev/)**: a whole array of useful web development tips, suggestions, and tutorials, curated by Google Web Developers. This also led me to understanding [web accessibility](https://web.dev/accessible/) and using [Google Lighthouse](https://developers.google.com/web/tools/lighthouse) for tracking performance, accessibility, and SEO metrics.

- **[Open Graph Protocol](https://www.freecodecamp.org/news/what-is-open-graph-and-how-can-i-use-it-for-my-website/)**: basically, extra HTML header tags to enrich your content for display on social media.
