---
title: "New Projects"
categories:
  - Lab Blog
tags:
  - cudmorelab
---

We have a number of projects we want to continue to develop and a number of exciting new projects we want to get off the ground.

We are writing code to extend the Python based image viewer called [Napari]. This includes writing plugins to manage our image analysis pipelines to (i) load, (ii) analyze, (iii) visualize, and (iv) save.

To begin making a Napari plugin, check out [this documentation](https://napari.org/plugins/stable/index.html).

Each of these projects will follow our development workflow by first create a general purpose backend Python engine (that can be used by others) and then writing interface code to (in this case) visualize our data and analysis in Napari.

## Some Example Projects

1. Load and analyze Ca<sup>++</sup> imaging movies using [CaImAn]. 

2. Load and analyze Super resolution microscopy images using [AICS-Segmenter]. **Good news!** The folks at the Allen Institute for Cell Science (AICS) have recently created a [Napari plugin](https://www.allencell.org/segmenter.html) for the AICS Segmenter Python engine.

3. Load and analyze Kymograph images (see Sparks).

4. Load and visualize existing [MapManager] analysis.


[Napari]: https://napari.org

[caiman-github]: https://github.com/flatironinstitute/CaImAn
[CaImAn]: https://caiman.readthedocs.io/en/master/

[aics-segmenter]: https://github.com/AllenCell/aics-segmentation

[MapManager]: https://mapmanager.net