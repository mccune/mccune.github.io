---
layout: post
title: So Which GH To Revit Plugin Should I Use?
date: 2013-05-05 23:19
author: michael
comments: true
categories: [CASE, Chameleon, Geometry Gym, Grasshopper, Hummingbird, Interoperability, Revit, Rhino]
---
&nbsp;

The short answer is all of them! Each of the GH to Revit plugins I briefly covered for Adaptive Components can fill a need depending on what you are trying to achieve, how often you will be updating, how big the project is, and among other things. Without being biased, below are a few suggestions on which one to use in certain scenarios taking into consideration the current development state of each plugin. With the update frequency of a few of these plugins, these suggestions may change drastically.

&nbsp;

&nbsp;
<h3>Chameleon</h3>
<ul>
	<li>If you want a simple to use plugin.</li>
	<li><span style="line-height: 13px;">If you are working on one machine and will only be transferring Adaptive Components.</span></li>
	<li>If you want to create custom Curtain Wall Grid patterns in Revit.</li>
	<li>If you need to bring geometry from Revit to Grasshopper as a Mesh, Surfaces, Curves, etc.</li>
</ul>
<em><a title="Grasshopper &amp; Revit Interoperability: Adaptive Components via Chameleon" href="http://collectivebim.com/grasshopper-revit-interoperability-chameleon/">link to Chameleon post</a></em>

[divider top="0"]

&nbsp;
<h3>Hummingbird</h3>
<ul>
	<li>If you need to place Revit specific elements that are not available in other plugins at the moment like:
<ul>
	<li>Lines</li>
	<li>Loft Forms</li>
	<li>Masses</li>
	<li>Rooms</li>
	<li>Topography</li>
</ul>
</li>
	<li>If you want a fairly simple to use plugin.</li>
	<li>If you also need to connect the data to Processing or Cinema 4d.</li>
</ul>
<a title="Grasshopper &amp; Revit Interoperability: Adaptive Components via Hummingbird / Whitefeet" href="http://collectivebim.com/grasshopper-revit-interoperability-hummingbird/"><em>link to Hummingbird post</em></a>

[divider top="0"]

&nbsp;
<h3>Geometry Gym</h3>
<ul>
	<li>If you need to bring over geometry that does not necessarily have to be native Revit elements, but recognized as a specific element type like:
<ul>
	<li>Stair</li>
	<li>Railings</li>
	<li>Coverings</li>
	<li>Roofs</li>
	<li>etc</li>
</ul>
</li>
	<li>If you need to make more than just Architectural elements like:
<ul>
	<li>Structural
<ul>
	<li>Beams</li>
	<li>Columns</li>
	<li>Trusses</li>
	<li>Plates</li>
	<li>Bolts</li>
</ul>
</li>
	<li>Mechanical, Electrical, Plumbing, Fire Protection
<ul>
	<li>Ducts</li>
	<li>Lighting Fixtures</li>
	<li>Pipes</li>
</ul>
</li>
</ul>
</li>
	<li>If you need to connect to additional platforms other than Revit through IFC like:
<ul>
	<li>Tekla &amp; Tekla BIMsight</li>
	<li>SDNF</li>
	<li>AutoCAD Architecture &amp; AutoCAD MEP</li>
	<li>ArchiCAD</li>
	<li>Solibri</li>
</ul>
</li>
	<li>If you want to learn IFC in the process as a bonus!</li>
	<li>If you want development and support with the tools.</li>
</ul>
<em><a title="Grasshopper &amp; Revit Interoperability: Adaptive Components via Geometry Gym" href="http://collectivebim.com/grasshopper-revit-interoperability-adaptive-components-geometry-gym/">link to Geometry Gym post</a></em>

[divider top="0"]

&nbsp;
<h3>CASE workflow tools</h3>
<ul>
	<li>If you don't want to delete your geometry every time you update your Grasshopper definition.</li>
	<li>If you want a simple to use plugin.</li>
	<li>If you are working on multiple machines.</li>
	<li>If you need to share your data securely and efficiently with teams in far far away places.</li>
	<li>If you need to place native Revit "Hosted" elements like:
<ul>
	<li>Doors</li>
	<li>Windows</li>
	<li>Wall Hosted</li>
	<li>Floor Hosted</li>
	<li>Ceiling Hosted</li>
</ul>
</li>
	<li>If you want development and support with the tools and process.</li>
</ul>
<em><a title="Grasshopper &amp; Revit Interoperability: CASE workflow tools" href="http://collectivebim.com/grasshopper-revit-interoperability-case-workflow-tools/">link to CASE post</a></em>

<a href="http://www.theprovingground.org/2013/05/spring-workshop-recap-parametric.html" target="_blank"><em>link to Nate's post on the tools and their implementation at recent workshops</em></a>

[divider top="1"]

&nbsp;

With most of the use cases out on the table, let's take a look at their performance in a side-by-side comparison.

&nbsp;
<h3>Speed</h3>
One of the biggest and most apparent difference between them all are the speeds that they transfer the geometry over from Grasshopper to Revit. Using the same data set as in the previous posts, I unofficially timed each plugin through a series of steps. First, I recomputed the Grasshopper definition. Second, I exported the file from Grasshopper. Third, I imported the file into Revit. Fourth, I updated a parameter and re-exported the file from Grasshopper. Finally, I re-imported the file into Revit to change that parameter value.
<p style="text-align: center;"> <img class=" wp-image-889 aligncenter" alt="GH to Revit_Transfer Speed" src="http://collectivebim.com/wp-content/uploads/2013/05/GH-to-Revit_Transfer-Speed.jpg" width="626" height="566" /></p>

<h3 style="text-align: left;">Speed Chart Summary:</h3>
<ul>
	<li><span style="line-height: 12.997159004211426px;"><strong>Chameleon</strong> came in first in the speed test. If you are using Adaptive Components, Chameleon would be the way to go. If you need other geometry types, you will have to use another plugin.</span></li>
	<li><strong>Hummingbird</strong> came in last. With other geometry types that involve sketching lines, which involve point definitions, the time is increased dramatically as it is additional lines to parse though line by line.</li>
	<li><strong>Geometry Gym</strong> came in third. The speed with this plugin also greatly depends on what elements you are placing as it may require a bunch of IFC definitions to describe a geometry type. There really is no update parameter workflow with Geometry Gym, so instead you have to re-import the IFC.</li>
	<li><strong>CASE</strong> workflow tools came in second squeezing just in front of Geometry Gym mainly due to the update parameter tool that allows the CASE workflow tools to just change that value without recreating the geometry.</li>
</ul>
<p style="text-align: left;">[divider top="1"]</p>

<h3>File Size</h3>
<p style="text-align: left;">Though File size does not seem to have a significant impact in the workflow speed, it does add an additional layer of management to the process.</p>
<p style="text-align: left;"><img class=" wp-image-890 aligncenter" alt="GH to Revit_File Size" src="http://collectivebim.com/wp-content/uploads/2013/05/GH-to-Revit_File-Size.jpg" width="572" height="370" /></p>

<h3>File Size Chart Summary:</h3>
<ul>
	<li><strong>Chameleon</strong> tied for first with the CASE workflow tools as it does not actually require a file to transfer the data. It establishes a live link instead.</li>
	<li><strong>Hummingbird</strong> came in third.</li>
	<li><strong>Geometry Gym</strong> came in last, which is not really a surprise as IFC can get bulky.</li>
	<li><strong>CASE</strong> workflow tools tied with Chameleon for first. Though the CASE workflow tools transfers a file, it does it though a web management service that makes it hands-free and file-free.</li>
</ul>
[divider top="1"]
