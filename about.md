---
layout: page
title: About Me
---
<head>
<script src="http://canvasjs.com/assets/script/canvasjs.min.js"></script>
<script type="text/javascript">

window.onload = function () {
	var chart = new CanvasJS.Chart("chartContainer", {
		theme: "theme2",//theme1
		title:{
			text: "Basic Column Chart - CanvasJS"              
		},
		animationEnabled: false,   // change to true
		data: [              
		{
			// Change type to "bar", "area", "spline", "pie",etc.
			type: "column",
			dataPoints: [
				{ label: "apple",  y: 10  },
				{ label: "orange", y: 15  },
				{ label: "banana", y: 25  },
				{ label: "mango",  y: 30  },
				{ label: "grape",  y: 28  }
			]
		}
		]
	});
	chart.render();
}
</script>
</head>
<p class="message">
  Hey there! I am Vamsidhar Reddy Gaddam or simply Vamsi.
</p>


I am currently an engineer at [ARM](http://www.arm.com/). I graduated with a *PhD
in Computer Science* from *University of Oslo*. My mind wanders among
programming, science, hiking and random thoughts about *everything* under the
sun. 

![You know my name]({{ site.url }}/assets/images/penguin1.jpg){:height="400px"}

Just drop me a message if you would like to have a tutorial blog post about
anything related Image processing, computer vision, graphics or parallel
programming. 

<div id="chartContainer" style="width: 300px; height: 400px;"></div>
