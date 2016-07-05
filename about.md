---
layout: page
title: About Me
---
 <head>
    <script type="text/javascript" src="https://www.gstatic.com/charts/loader.js"></script>
    <script type="text/javascript">
      google.charts.load('current', {packages:["orgchart"]});
      google.charts.setOnLoadCallback(drawChart);

      function drawChart() {
        var data = new google.visualization.DataTable();
        data.addColumn('string', 'Name');
        data.addColumn('string', 'Manager');
        data.addColumn('string', 'ToolTip');

        // For each orgchart box, provide the name, manager, and tooltip to
        // show.
data.addRows([
		  ['Mike','',''],
		  ['Jim', 'Mike',''],
          ['Alice', 'Mike', ''],
          ['Bob', 'Jim', 'Bob Sponge'],
          ['Carol', 'Bob', '']
        ]);

        // Create the chart.
        var chart = new google.visualization.OrgChart(document.getElementById('chart_div'));
        // Draw the chart, setting the allowHtml option to true for the
        // tooltips.
        chart.draw(data, {allowHtml:true});
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

<div id="chart_div" style="width: 600px; height: 400px;"></div>
