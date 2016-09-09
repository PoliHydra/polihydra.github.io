---
layout: page
title: Home
name: The Polihydra Project
robots: noarchive
---
# The Polihydra Project

The Polihydra Project is a collection of resources for the Finite
Element simulation of [hydrogen
embrittlment](https://en.wikipedia.org/wiki/Hydrogen_embrittlement) in
mechanical parts and structures.

<figure markdown="1">

![Pipe section with circumferential
 crack.](/images-p/Steel-with-Hydrogen-Induced-Cracks-01.jpg)

<figcaption markdown="1">
Hydrogen induced cracks. <cite>Photo by CEphoto, Uwe Aranas /
CC-BY-SA-3.0, source [Wikimedia Commons][hic]</cite>
</figcaption>

</figure>

[hic]: https://commons.wikimedia.org/wiki/File:Steel-with-Hydrogen-Induced-Cracks-01.jpg

## Hydrogen embrittlement

*Hydrogen embrittlement* is a form of metal degradation, well
recognized since several years, caused by mechanisms acting and
interacting at the microscopic and atomic scales which are currently
under investigation. Hydrogen embrittlement occurs in many industrial
applications, as oil&gas infrastructures, pipelines for hydrogen
transportations, vessels for hydrogen storage.

The deleterious macroscopic effect of the environmental adsorption of
atomic hydrogen into a steel lattice is the loss of ductility, thus a
decrease in mechanical properties.  Recently scientists, guided by
extensive experimental observations, made some efforts in the
development of numerical models able to simulate the effect of
hydrogen on different steels. Such tools are especially useful for the
design of components working in extreme conditions.  Nevertheless, the
simulation of this complex phenomenon, which includes different
physical parameters and the coupling of diffusion and mechanical
fields, is a challenging issue.

## Finite element simulation

The total hydrogen concentration is composed by two contributions in
mutual equilibrium: the hydrogen concentration in the normal
interstitial lattice sites (NILS), which is driven by the hydrostatic
stress gradient, and the hydrogen concentration in the reversible
trapping sites. At present, no commercial Finite Element software has
builtin the ability of simulate hydrogen diffusion and predict the
total hydrogen concetration, hence the need to implement *ad hoc* procedures.


The aim of the Polihydra Project is to study hydrogen embrittlement in
steels through Finite Element simulations. All code produced will be
released open source and will be available for
[download](/download/). The aim of this site is to share code, to
provide a guideline to the methodology, but also to the practical use
of the finite element simulations.
