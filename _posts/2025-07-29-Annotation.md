---
title: Multi-Level Annotation in FUSION
date: 2025-07-29 09:41:16 +0400
categories: [Tasks, Annotation, Components, Tutorials]
tags: [fusion, preprocessing, usage, tutorials]
author: sam
description: Annotating data in FUSION
toc: true
media_subpath: /assets/img/annotation/
---

# Annotating Data in *FUSION*

*FUSION* provides multiple different ways to generate annotations for histology data. These different components function at different levels in specificity and efficiency in annotation, generally following this hierarchy:

![ann-hierarchy-fig](ann-hierarchy-fig.png)
_Figure representing the different types of annotations available in FUSION. Slide Annotations are labels applied to an entire slide. Feature Annotations are labels applied to individual structures. Bulk Labels are labels applied to multiple structures at the same time._

# Slide Annotation

Annotation of slides is accomplished using the `SlideAnnotation` component in *fusion-tools*. This component allows for loading multiple different *schemas* for annotations. These *schemas* contain information on the particular labeling task, such as the name, description, user specifications (not yet implemented), and what annotations are required. Below are some examples of the types of annotations available for the `SlideAnnotation` component.

![slide-annotation-fig](slide-annotation-fig.png)
_The SlideAnnotation component allows for multiple different types of labels to be applied to an entire slide. In addition to text, numeric, and options labels, any label type may also be accompanied by a region of interest (ROI) which can provide additional justification for the annotated label._


# Feature Annotation

Annotation of individual structures on a slide is accomplished using the `FeatureAnnotation` component in *fusion-tools*. In *GeoJSON* terms, each structure in *fusion-tools* is a *Feature* that is part of a *FeatureCollection* (hence the name of this component). This component enables users to generate image masks which are inherently linked to a specific structure on a slide, as well as text, options, and numeric labels. This component also lets users "pin" different annotation components so that they are readily accessible for quick annotations of many structures.

![feature-annotation-fig](feature-annotation-fig.png)
_The FeatureAnnotation component allows for assigning labels to individual structures in a slide. These labels include text, numeric, or options labels as well as overlaid image masks._

# Bulk Labels

When applying the same label to multiple structures, user's can specify two different sets of filters in order to narrow down the included structures. The first set are spatial filters where the user can select a number of different spatial predicates to include or exclude structures based on. The second set lets users set ranges within (or not within) which to include structures based on their value for a specific property. 

This enables the creation of complex sets of queries such as, "Show me all the structures within 50 pixels of this structure that don't intersect with this other structure, that have an area within this range".

Structures can then be manually pruned by double-clicking the markers on top of unwanted structures.

![bulk-labels-fig](bulk-labels-fig.png)
_The BulkLabels component allows users to assign the same label to multiple structures at the same time. By combining both spatial and property filters, users can form complex inclusion criteria for new structures which can then be downloaded in JSON format._









