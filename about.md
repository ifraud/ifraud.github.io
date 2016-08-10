---
layout: page
title: About Me
---
<p class="message">
  Hey there! I am Vamsidhar Reddy Gaddam or simply Vamsi.
</p>


I am currently an engineer at [ARM](http://www.arm.com/). I graduated with a *PhD
in Computer Science* from *University of Oslo*. My mind wanders among
programming, science, hiking and random thoughts about *everything* under the
sun. 

![You know my name]({{ site.url }}/assets/images/penguin1.jpg){:height="400px"}

Just drop me a message here, if you would like to have a tutorial blog post about
anything related to Image processing, computer vision, graphics or parallel
programming. If you want to collaborate or contribute content, I would be gladly
up for it. In general, I am always up for new ideas!

That is it!

## A Dropping ball

Now, let us see how these concepts help us in physical world. Let us take a random planet with g=2 and no atmosphere. If we drop a ball from some height and 
see the change in height as a function of time elapsed. The dropping ball looks the following way.


<style>
#myContainer {
  width: 50px;
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
<button onclick="myFall()">Animate the ball</button>
</p>

<div id ="myContainer">
<div id ="myAnimation"></div>
</div>

<script>
function myFall() {
  var elem = document.getElementById("myAnimation");
  var pos = 0;
  var t = 0;
  var id = setInterval(frame, 10);
  elem.style.left = 175;
  function frame() {
    if (t == 15) {
      clearInterval(id);
    } else {
      t++;
      elem.style.top = t*t + 'px';
    }
  }
}

function myMove1() {
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
 
<p>
<button onclick="myMove1()">Animate the ball</button>
</p>

<div id ="myContainer">
<div id ="myAnimation"></div>
</div>

