---
layout: post
title: "An old friend's calculus problem"
date: 2016-05-27 08:00:00
comments: true
categories: mathematics, calculus
published: false
---

Helge an old friend to my family is a 96 year old inventor and engineer.
He can sing opera and will tell you stories that will make you cringe
and laugh your heart out.

One of his many favourite pastimes is to solve mathematical puzzles
and riddles, and he mischievously loves to pose NP-hard problems, even
those proven to be impossible to solve, to others.

However, I was fortunate enough to have reached enough mathematical maturity
through my years of studying at [http://cs.lth.se](LTH) that I could
answer one of his most recent mental inventions.

# The problem
``` none Suppose there is a cone with a height of 10 meters and a
diameter of 1 meter.  At the tip of this cone a rope is attached. At
the other end of the rope is a bird that is flying in circles around
the cone, with a decent of 1m per circle such that it makes 10 lapses
around the cone when the end of the rope ends at the bottom of the
cone.

How long is the rope?  ```

# Solution My first approach was to reach some kind of mental model of
the problem.  It's easy to visualise the cone with the curve
represented by the rope, following the cone's surface area.

It would look something like this:

``` text
            .               |                ;
           /.\              |  1st lap       ;
          /  .\             |                ;
         /.    \               |             ;
        /   .   \              |  2nd        ;
       /      .  \             |      lap    ;
      /          .\            |             ;
     / .           \        |                ;
    /    .          \       |   Nth          ;
   /        .        \      |       lap      ;
       !!  SNIP !!          |                ;
 /                   . \       |  10th       ;
.-----------------------       |       lap   ;
```

After some thinking I thought that an upper bound could be expressed
by folding out the curve as a large triangle who's hypotenuse is
actually the hypotenuse of 10 consecutive triangles. Each triangle's
hypotenuse would be 10 % smaller than the one previous, then the
length of the curve would be the sum of the length of the 10
hypotenuse's.

Since the diameter is one, the length of the base cathetus of the
first triangle would be $2\pi$, and the height of the opposite
cathetus would be $1$.

However I quickly realised that the decent of the cone has to be taken
into account.

I had to do some research, but I learnt that if you can parameterise
the curve, we can calculate the length using $\int_{a}^{b}
|\overline{r}'(t)|\ dt$ where $|\overline{r}'|$ is the length of the gradient of
parameterisation of the curve.

$$
    \overline{r} = (cos(20 \pi t)(1-t), sin(20 \pi t) (1-t), 10t)
$$
