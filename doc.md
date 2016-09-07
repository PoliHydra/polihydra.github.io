---
layout: page_WIP
title: Documentation
robots: noindex
permalink: /doc/
---
# {{ page.title }}

<figure markdown="1">
![A 17th century print representing the Lernaean Hydra.](/myth/hydra.png)
<figcaption markdown="1">
Lernaean Hydra (Image source: [Wikimedia Commons](
https://commons.wikimedia.org/wiki/File:Hydra_(creature).jpg))
</figcaption>
</figure>

## Implementation

Here we present a weakly coupled formulation of hydrogen diffusion
with stress-strain analysis that follows a 3-step procedure:

1. an initial static analysis
2. a mass diffusion analysis
3. a final static analysis including cohesive elements

These cohesive elements simulate failure of the material (i.e. the
presence of a crack and its opening) in presence of environmental
hydrogen uptake. This considers a mechanism of local decohesion
(Hydrogen Enhanced DE-cohesion, HEDE), which directly acts decreasing
the cohesive strength of these finite elements.  With this aim, we
tailored the formulation of cohesive elements with an extensive use of
Abaqus user subroutines in Fortran. Simple examples of code
application to 2D cases are included in the website, to support the
description and to share our finding and make it fully replicable.
