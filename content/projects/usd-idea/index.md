+++
title = "usd-idea"
date = 2019-05-11

[taxonomies]
categories = ["software"]

[extra]
featured_image = "img.png"
repo_path = "justint/usd-idea"
+++
A plugin for JetBrains IDEs (PyCharm, IntelliJ, etc) that provides support for Universal Scene Description (USD).
<!-- more -->

[![JetBrains IntelliJ Plugins](https://img.shields.io/jetbrains/plugin/v/12407-usd.svg?style=popout)](https://plugins.jetbrains.com/plugin/12407-usd)
[![JetBrains IntelliJ plugins](https://img.shields.io/jetbrains/plugin/d/12407-usd.svg?style=popout)](https://plugins.jetbrains.com/plugin/12407-usd)

<p style="text-align: center; font-weight: bold"><a href="https://plugins.jetbrains.com/plugin/12407-usd">Install (via JetBrains Marketplace)</a> ◦ <a href="https://github.com/justint/usd-idea">GitHub</a></p>

A plugin for JetBrains IDEs (PyCharm, IntelliJ, CLion, etc) that provides support for [Universal Scene Description (USD)](https://graphics.pixar.com/usd/docs/index.html), a framework for interchange of 3D computer graphics data, developed by Pixar Animation Studios.

Released under the [MIT License](https://github.com/justint/usd-idea/blob/main/LICENSE).

# Feature set

  - `.usd`/`.usda` filetype syntax highlighting & validation
  - Asset/prim reference navigation (with `usdresolve`)
  - Brace matching & block folding
  - Structure/outline views
    
# Future aspirations

JetBrains has an incredibly powerful [Program Structure Interface (PSI)](https://plugins.jetbrains.com/docs/intellij/psi.html) within their editors that represent the code's syntactic and semantic models, and powers their intellisense features and autocompletion.

Pixar's USD has an equally powerful [layer composition](https://graphics.pixar.com/usd/files/Siggraph2019_USD%20Composition.pdf) system which can represent 3D scenes as being composed from many elemental assets.

**By fully utilizing the JetBrains PSI to model USD's layer composition system, usd-idea could evolve into a substantially effective USD file editor, inspector, and debugger.** 

Listed below are noteworthy features I'm interested in adding into the plugin:

- ## Crate/package (`.usdc`/`.usdz`) file support

  File viewing/editing of USD crate (`.usdc`) and package (`.usdz`) file support.

  Crate file support has been a long-time desire[^1] and unfortunately, a pain in the butt to implement within the IntelliJ SDK. I've made some promising advancements in recent tests (as of September 21, 2021) and will hopefully have a partially working form of this in the near future.

- ## USD Python API autocompletion

  Autocompletion for USD's Python bindings (e.g.: `pxr.Usd`, `pxr.Sdf`, etc).

  Some attempts towards this have been tried by others using Python-stub based methods[^2], but unfortunately no USD stubs have ever been publicly released, officially or non-officially.

  Depending on how robust PyCharm's SDK is, I may end up attempting a similar approach to usdstubgen by inspecting the Python packages & modules in a runtime context within the plugin and serving the autocomplete results back to the IDE.

- ## `usdchecker` file linting

  File inspections provided by `usdchecker`'s rules and metrics.
  
- ## Prim/property navigation
  
  Navigation of declarations, overs, and usage of prims/properties. 
  
  Would be excellent to have value inspections too.
  
- ## Inline documentation

   USD documentation (Doxygen and/or graphics.pixar.com) directly viewable from object inspecting & mouseovers.
    
- ## Layer stack/composition explorer
  
  It would be nice to explore the layer stacks in some sort of tree view, similar to usdview's Composition Explorer.

- ## Hydra renderer viewport

  Interactive viewport within the IDE, with live updating as files are edited.
  
  Perhaps with [JNA](https://github.com/java-native-access/jna); more research & investigations needed.
  
  - [HdEmbree docs](https://graphics.pixar.com/usd/docs/api/hd_embree_page_front.html)
  - [testHdEmbree.cpp](https://github.com/PixarAnimationStudios/USD/blob/dc710925675f7f58f7a37f6c18d046a687b09271/pxr/imaging/plugin/hdEmbree/testenv/testHdEmbree.cpp)
  
If any of these features pique your interest, or if you have ideas of your own, please reach out and let me know! I'd love to hear how you might imagine using an IDE with USD, or have ideas how to build it.
  
[^1]: [https://github.com/justint/usd-idea/issues/7](https://github.com/justint/usd-idea/issues/7): _Add support for binary USD files_

[^2]: [usdstubgen](https://github.com/chadrik/usdstubgen) by Chad Dombrova