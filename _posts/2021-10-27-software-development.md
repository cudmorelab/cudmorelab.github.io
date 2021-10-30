---
title: "Software Development In The Lab"
categories:
  - Lab Blog
tags:
  - cudmorelab
---

# Overview

We are writing new code and extending the features of existing **Cudmore Lab** code, including:

## 1) [SanPy]

Designed for electrophysiology. We want to extend this to include voltage clamp analysis.

## 2) Ca<sup>++</sup> image analysis

Including both Kymographs from line scans and full field-of-view Ca<sup>++</sup> imaging movies.

## 3) Super resolution microscopy

Image analysis at the nanometer scale.

## 4) [PyMapManager][pymapmanager]

See [Map Manager User documentation][mapmanager.net]. A good starting point for making web-based apps.

# Overview of software analysis pipeline

Our development is accomplished in a number of steps.

1.  We first create a Python **backend** for file loading, analysis, and saving. This acts as our main computational engine and relies heavily on standard Python packages such as [NumPy], [Pandas], and [SciPy]. We also provide thourough code documentation, Unit Testing, and [Jupyter] notebooks describing how to use the code.

2. We then wrap the **backend** in interface code to provide an easy to use point-and-click desktop GUI. These desktop GUIs are using a combination of [Napari], [PyQt].

3. We then use the **backend** to create simple to follow and descriptive [Jupyter] notebook recipes that describe how to use our code in a script.

4. Ultimatley, we wrap the **backend** in interface code to run in the cloud and in a browser. For this, we use a number of tools and languages including [Javascript] frameworks such as [Vue], microservices like [Flask] and [FastApi], and [Docker] containers. We also deploy these interfaces on distributed cloud platforms such as [Amazon AWS] and [Heroku].



# Python packages we are using

This is all super exciting. Python has come of age and the future is not bounded.

### a) For backend analysis we use a number of standard Python packages

- [numpy][numpy] - Number crunching of n-dimensional arrays
- [pandas][pandas] - Tabular data like froma comma-seperated-values (csv) file
- [scipy][scipy] - General purpose image analysis
- Lots of others!

### b) We also use a number of customized image analysis packages

These are all actively maintained with a ton of people contributing. This is hard-core stuff and we can use it!!!

- [CaImAn] - From FlatIron Institute, see [caiman-github][caiman-github]. Used to detect regions-of-interest from Ca<sup>++</sup> movies.
- [AICS-Segmenter] - from Allen Institute of Cell Science. Used to segment 3D image volumes from laser-scanning or super-resolution microscopy.
- Sparks - No link yet, not sure if they seperate their back-end from front-end. This can be used to analyze Kymographs.

### c) For desktop GUI interfaces, we use

- [Napari][napari-docs] - from Chan-Zuckerberg, see [napari-github][napari-github]. This is an exciting game-changer. It uses PyQt and has a relatively easy to follow plugin architecture.
- [PyQt][pyqt] - A package to make cross platform GUIs. This is critical and the most stable of all. It is based on the original C++ [Qt][qt].
- [PyQtGraph][pyqtgraph] - An extension of PyQt that makes plotting super easy. Super important!!! The original developer has partnered with others to make a newer visualization engine called [VisPy](https://github.com/vispy/vispy), more on that later. See user documentation [here](https://vispy.org/).


### d) For web/cloud GUI interface, we use

This is the tricky part. For some reason, traditional Computer Science (C, C++, Python, etc) has diverged from the front-end web. In order to make GUIs on the web, we are stuck with Javascript and it is a bit different from its more traditional Computer Science counterparts.

- [Javascript][javascript] framework

- [Vue][vue]. This is designed by a former Google developer and is gaining lots of trackshion, has a good user-base, and should be the most straight-forward to implement

- We have have some code written in [Plotly Dash][dash]. This simplifies things as most code is written in Python rather than Javascript. See [SanPy repository](https://cudmore.github.io/SanPy/web-application/)

 - We could also use [Angular][angular] from Google or [React][react] from FaceBook.


# Command line interface (CLI)

To make all this work, on a day-to-day basis we almost entirely use a command line interface (CLI). This includes CLI on macOS and Linux (which are very similar) and Microsoft Windows (which is rogue). We use the command line to install, interpret, and run our Python code.

# Code editors

Editing our code is the most important thing we do! Use any text-editor you like but we strongly suggest one of [Atom][atom], [VS Code][vscode], or [PyCharm][pycharm].

Each of these provides rich project managment. **VS Code** might be best and yes, it is made by Microsoft.

It is wise to just start using one of these as a text editor and then use it for advaced features later.

# Code documentation

As you write code, it is **super important** to add documentation. If done correctly, this can be used to auto-generate API documentation for the code, like [here for MapManager][pymapmanager-api] and [here for SanPy](https://cudmore.github.io/SanPy/api/bAnalysis/).

Commenting code is no longer free form, you should follow some standards that are generally called **DocString**(s).

I generally use the [Google DocString](https://sphinxcontrib-napoleon.readthedocs.io/en/latest/example_google.html) format.

Once you have some working code, you then want to write more narrative descriptions of how to use it, describe the GUI, give your methods, and expose your pitfalls. In general, we use [MkDocs] and when feeling fancy use [Spinx][sphinx].

MkDocs is driven by text files written in the [markdown](https://daringfireball.net/projects/markdown/) format. We find this awesome, easy, and everything is just text. For example, this document you are reading is written in Markdown!

# Jupyter notebooks

Aside from creating Desktop and Web based GUIs, we want to create Advanced-Programmin-Interfaces (APIs) so users can harness the power of our code with simple and short scripts.

To do this, we use [Jupyter Notebooks][jupyter].

# Unit testing

This is an area we (e.g. I) am learning. The idea is you need to write code that tests that your main code returns expected results (kind of circular). This is useful when a code base gets large, like 10,000 or 100,000 lines of code.

For this we are starting to use [PyTest] and [Tox].

# Distributing one-click install applications

All this code and CLI based stuff is really fun, neat, and powerful. Yet, we need to put these tools into the hand of mere-mortals (e.g. Biologists). To do this we package our GUI applications into one-click installers using [PyInstaller].


[pymapmanager]: https://cudmore.github.io/PyMapManager/
[SanPy]: https://cudmore.github.io/SanPy/
[mapmanager.net]: https://mapmanager.net

[atom]: https://atom.io/
[pycharm]: https://www.jetbrains.com/pycharm/
[vscode]: https://code.visualstudio.com/

[pymapmanager-api]: https://pymapmanager.readthedocs.io/en/latest/
[mkdocs]: https://www.mkdocs.org/
[sphinx]: https://www.sphinx-doc.org/en/master/

[vue]: https://vuejs.org/
[angular]: https://angular.io/
[react]: https://reactjs.org/


[numpy]: https://numpy.org/
[pandas]: https://pandas.pydata.org/
[scipy]: https://www.scipy.org/

[Napari]: https://napari.org

[caiman-github]: https://github.com/flatironinstitute/CaImAn
[CaImAn]: https://caiman.readthedocs.io/en/master/

[aics-segmenter]: https://github.com/AllenCell/aics-segmentation

[napari-docs]: https://napari.org
[napari-github]: https://github.com/napari/napari

[pyqt]: https://riverbankcomputing.com/software/pyqt/intro
[pyqtgraph]: https://www.pyqtgraph.org/
[qt]: https://en.wikipedia.org/wiki/Qt_(software)

[javascript]: https://www.javascript.com/
[dash]: https://dash.plotly.com/

[jupyter]: https://jupyter.org/

[PyTest]: https://pytest.org
[Tox]: https://tox.wiki/en/latest/index.html

[pyenv]:https://github.com/pyenv/pyenv

[PyInstaller]: https://www.pyinstaller.org/

[Flask]: https://flask.palletsprojects.com/en/2.0.x/
[FastApi]: https://fastapi.tiangolo.com/
[Docker]: https://www.docker.com/
[Amazon AWS]: https://aws.amazon.com/
[Heroku]: https://en.wikipedia.org/wiki/Heroku
