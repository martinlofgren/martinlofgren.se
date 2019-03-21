---
title: "From Bézier Curve to Cartesian Equation"
date: 2019-03-21T21:52:02+01:00
draft: false
tags: [airship]
hasMath: true
---

It's been a while since working on the airship project, and since writing
about it here; it's been a lot to do in school and at work. This post has been
lying around for a month, but for some reason I did not publish it. 

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
At first, this seemed lika a trivial transformation: just solve for
{{< tex >}} y {{< /tex >}} and eliminate {{< tex >}} t {{< /tex >}}, right?
Doing this, we would arrive at a cubic equation. Now, solving a cubic equation
sure is feasible, but it involves quite some work. Maybe this is something I 
will do at a later moment, but at his stage I would rather use some easier approach.

The easy though not-so-elegant method I came up with was to calculate lots of
points along the curve by stepping {{< tex >}} B(\Delta_n) {{< /tex >}}
in the interval {{< tex >}} [0,1] {{< /tex >}}for some
small {{< tex >}} \Delta_n {{< /tex >}} and collect the results in a list.
In this manner, we have a list of points along the curve, ordered by 
{{< tex >}} x {{< /tex >}}. To find a good approximation of 
{{< tex >}} f(x) {{< /tex >}}, we simply do a lookup in the list for
{{< tex >}} x {{< /tex >}}. If we denote this function[^1]
{{< tex >}} \hat{f}(x) {{< /tex >}}, we see that 
{{< tex >}} \hat{f}(x) \to f(x) {{< /tex >}}as 
{{< tex >}} \Delta_n \to 0 {{< /tex >}}.

[0]: {{< relref path="deriving-a-formula-for-the-envelope" >}}
[^1]: Although it might be dubious whether this really is a function in the mathematical sense of the word, it can be treated so in the numerical calculation contexts we will be using it.
