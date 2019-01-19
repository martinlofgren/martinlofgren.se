---
title: "Deriving a Formula for the Envelope"
date: 2019-01-18T11:48:19+01:00
draft: false
tags: [airship]
hasMath: true
---

In order to ease the design of the airship, I've been elaborating with different
ways to describe the envelope with an equation:

- [Cycloid graphs][0]
- [The Folium of Descartes][1] rotated clockwise 45°
- An half ellipsis with tangential lines drawn to make a sharp corner.

All these attempts seemed overly complicated, or was not flexible enough to
describe an arbitrary airship envelope. I had to find something else.

Sketching the envelope in Inkscape using the path tool, it occured to me that
the tool I was using was a simple mathematical one: the [Bézier curve][2]. Using
the front and rear of the airship as endpoints of the curve, and two additional
control points, we can approximate the Bodensee envelope quite well. In the
following plot the beizer curve is drawn in red; the curve is also reflected in
the x axis to give a better visualization of the profile.

![Bezier curve approximating airship envelope](/img/envelope-bezier.png)

The control points were determined by trail-and-error to be
{{< tex display="" >}}
\begin{cases}
  P_0 = (0,0), \\
  P_1 = (0.195L,1.138R_{max}), \\
  P_2 = (L, 1.208R_{max}), \\
  P_3 = (L,0) 
\end{cases}
{{< /tex >}}

In this particular plot, {{< tex >}} L=2000 \text{ mm}, R_{max}=166\text{ mm}.
{{< /tex >}} These control points were plugged into the Bézier formula
{{< tex display="" >}}
  B(t) = (1-t)^3 P_0 + 3(1-t)^2 t P_1 + 3(1-t) t^2 P_2 + t^3 P_3,\; t \in [0,1].
{{< /tex >}}

The plot were made using Python and NumPy. The source code can be found in the
[git repo][3].

[0]: http://jwilson.coe.uga.edu/EMAT6680Fa2014/Gieseking/Exploration%2010/Parametric%20Equations.html
[1]: https://en.m.wikipedia.org/wiki/Folium_of_Descartes
[2]: https://en.wikipedia.org/wiki/B%C3%A9zier_curve
[3]: https://github.com/martinlofgren/airship/blob/master/calculations/envelope-formula.py
