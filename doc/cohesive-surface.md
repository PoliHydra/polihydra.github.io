---
layout: page_WIP
title: Cohesive surface
robots: noindex
mathjax: true
---
# {{ page.title }}

A cohesive surface is defined in Abaqus by means of

- a layer of cohesive elements, `*ELEMENT` card
- a `*COHESIVE SECTION` definition.
- a cohesive material, `*MATERIAL` card



## Traction Separation Law

The the traction separation law (TSL) links the three traction components
$$ (t_n , t_s , t_t) $$
across the cohesive surface to the separation components
$$ (\delta_n , \delta_s , \delta_t) $$. Abaqus assumes an intial linear
elastic behaviour, followed by damage initiation and evolution.
Accordingly three set of equations are to be defined, by using the following
cards within a `*MATERIAL` block:

{% highlight abaqus %}
*MATERIAL, NAME=<cohesive material name>
*ELASTIC, TYPE="TRACTION | COUPLED TRACTION"
*DAMAGE INITIATION, CRITERION="MAXE | MAXS"
*DAMAGE EVOLUTION, TYPE=DISPLACEMENT, SOFTENING=TABULAR
{% endhighlight %}

Although cohesive surfaces have no geometric “thikness”, Abaqus requires that
the elastic response to be defined on terms of stress--strain relations.  To
this purpose a “nominal” thickness $$T_0$$ and
“nominal strains” are defined

$$
\begin{align*}
\varepsilon_n &= \dfrac{\delta_n}{T_0}
&
\varepsilon_s &= \dfrac{\delta_s}{T_0}
&
\varepsilon_t &= \dfrac{\delta_t}{T_0}
\end{align*}
$$

These strains and $$T_0$$ have no physical meanining, therefore it is usual to
assume $$ T_0 = 1\cdot\text{unit-of-length} $$, so that the numerical values of
the strain components and separation components are equal.

{% highlight abaqus %}
*COHESIVE SECTION, ELSET=COHES, RESPONSE=TRACTION SEPARATION, MATERIAL=<cohesive material name>
<initial constitutive thickness>, <out-of-plane thickness>
{% endhighlight %}

### Linear elastic behaviour

* coupled behavior
  ^
    $$
    \begin{Bmatrix}
      t_n \\ t_s \\ t_t
    \end{Bmatrix}
    = 
    \begin{bmatrix}
      E_{nn} & E_{ns} & E_{nt} \\
      E_{ns} & E_{ss} & E_{st} \\
      E_{nt} & E_{st} & E_{tt} \\
    \end{bmatrix}
    \begin{Bmatrix}
      \varepsilon_n \\ \varepsilon_s \\ \varepsilon_t
    \end{Bmatrix}
    $$
* uncoupled behavior
  ^
    $$
    \begin{Bmatrix}
      t_n \\ t_s \\ t_t
    \end{Bmatrix}
    = 
    \begin{bmatrix}
      E_{nn} &        &        \\
             & E_{ss} &        \\
             &        & E_{tt} \\
    \end{bmatrix}
    \begin{Bmatrix}
      \varepsilon_n \\ \varepsilon_s \\ \varepsilon_t
    \end{Bmatrix}
    $$


*[TSL]: traction separation law

## 2D plane strain problems

Describe mesh with `COH2D4`

### Only normal separation

Describe simplifying assumptions.
