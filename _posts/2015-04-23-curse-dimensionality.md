---
layout: post
title: The curse of dimensionality
tags: ["R", "python", "machine learning", "programming"]
comments: true
---


## Introduction

Based on Peter Norvigs's MSRI talk
[What to demand from a Scientific Computing Language](http://www.msri.org/summer_schools/556/schedules/4197)
(22:50): 'if you have high dimensional data, then almost all the data
are outliers'. He showed a very elegant piece of python code to
illustrate it; below is an R implementation.

<!--more-->

{% include _toc.html %}

## Implementation

{% gist lgatto/6479628cfbce942b5def curse-of-dimensionality.py %}

The simulation generates `N` points in hypercubes of `d` dimensions
and counts how many of those points are outliers, defined as being in
the 1% outer shell of the space. In 1 dimension, we have 1% of the
uniformely distributed points that are outliers. In 50 dimension,
there are already 60% of the points that are outliers; in 100
dimensions, almost 90% of the points are outliers.

{% gist lgatto/6479628cfbce942b5def curse-of-dimensionality.R %}

## Result

![Curse of dimensionality](/images/curse-of-dimensionality.png)
