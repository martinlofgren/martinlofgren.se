---
title: "From Bézier Curve to Cartesian Equation"
date: 2019-02-02T21:52:02+01:00
draft: true
tags: [airship]
hasMath: true
---

In the [previous post][0] we derived a formula for the envelope using a Bézier
curve. Although the curve sure makes a good fit to the envelope, the formula is
of limited use in this form. In order to be able to perform a parametrized CAD
modell and to calculate the volume of the airship we would like to have a
function 
{{< tex >}} f: x \to y {{< /tex >}} for
{{< tex >}} x \in [0,L] {{< /tex >}}, 
{{< tex >}} L {{< /tex >}} being the length of the airship.
What we have in this formulation is a function 
{{< tex >}} B: t \to P {{< /tex >}} where 
{{< tex >}} P=(x,y) {{< /tex >}} and
{{< tex >}} t \in [0,1] {{< /tex >}}.

So how do we find this cartesian function {{< tex >}} f(x) {{< /tex >}}?
At first, this seemed lika a trivial transformation. It's just to solve for
{{< tex >}} y {{< /tex >}} and eliminate {{< tex >}} t {{< /tex >}}, right?
Doing this, we would arrive at a cubic equation. Now, solving a cubic equation
sure is feasible, but it involves quite some work. Maybe this is something I 
will do at a later moment, but at his stage another easier approach occured
to me.



[0]: {{< relref path="deriving-a-formula-for-the-envelope" >}}
