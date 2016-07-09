---
layout: post
title: The beauty of calculus
tags:
  - math
  - tut
---

Recently, a discussion with a friend made me realize that a lot of students are
taught calculus as a bunch of formulae and not as a useful concept to understand
several phenomena in the universe. To show the beauty of calculus, I decided to
write a small tutorial explaining the basic concepts of limits, differentiation
and integration. Immediately connecting these concepts, I will also show how
basic motion laws in physics can be interpreted.

## Slope

We will be using one and only one curve the whole tutorial, it will change its
purpose and meaning as we go by. But the curve will remain the same and between
the exact same points `P1 = (x1,y1)` and `P2 = (x2,y2)`.

`figure`

When we *graph* something, we are always showing a *relation* between the variables
plotted on the different axes. In effect, we can say that `y = f(x)`, where `f`
is some functions. Some of the examples could be:

> f(x) = x
> f(x) = $$a^2 + b^2 = c^2$$  




## A Moving Car
<style>
#myContainer {
  width: 400px;
  height: 400px;
  position: relative;
  background: yellow;
}
#myAnimation {
  width: 50px;
  height: 50px;
  position: absolute;
  background-color: red;
}
</style>

<p>
<button onclick="myMove()">Animate the car</button>
</p>

<div id ="myContainer">
<div id ="myAnimation"></div>
</div>

<script>
function myMove() {
  var elem = document.getElementById("myAnimation");
  var pos = 0;
  var id = setInterval(frame, 10);
  elem.style.left = 175;
  function frame() {
    if (pos == 350) {
      clearInterval(id);
    } else {
      pos++;
      elem.style.top = pos + 'px';
    }
  }
}
</script>
 
