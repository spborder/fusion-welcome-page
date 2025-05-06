---
title: FUSION in Jupyter Notebooks
date: 2025-05-05 23:41:13 +0400
categories: [Jupyter]
tags: [fusion-tools, jupyter]
author: sam
description: Loading FUSION visualizations in a Jupyter environment
toc: true
media_subpath: /assets/img/jupyter/
---

# Using FUSION in Jupyter Notebooks

In addition to web-deployment in a browser window, *FUSION* can also be added inline to any workflow in a Jupyter Notebook environment.

```python

from fusion_tools.visualization import Visualization
form fusion_tools.components import SlideMap, OverlayOptions


vis = Visualization(
	local_slides = ["list","of","local","slide","paths"],
	local_annotations = ["list","of","local","slide","annotations"],
	components = [
			[
				SlideMap(),
				OverlayOptions()
			]
		],
	app_options={
		'jupyter': True
	}
)
vis.start()

```

Running the following code in a Jupyter Notebook will produce the following output:

![jupyter-screenshot](jupyter-screenshot.PNG)
_Screenshot of FUSION in a Jupyter Notebook_

From this point, there are a number of different interactive, multi-step analyses which can be done. These include, manual annotations of image regions containing structures/characteristics of interest, filtering of structures by property or by spatial queries followed by downloading annotations, making image annotations and generating labeled masks which can be incorporated into deep learning training workflows, etc.



