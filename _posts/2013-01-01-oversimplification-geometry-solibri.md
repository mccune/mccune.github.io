---
layout: post
title: Fixing oversimplification of complex geometry in Solibri.
date: 2013-01-01 21:34
author: michael
comments: true
categories: [BIM, Solibri, Tips &amp; Tricks]
---
&nbsp;

When Solibri's <a href="http://www.solibri.com/solibri-model-viewer.html">Model Viewer</a> and <a href="http://www.solibri.com/solibri-model-checker.html">Model Checker</a> open and import model files, the geometry is simplified into triangulated faces. This allows the program to quickly render and check the geometry, but this sometimes leads to less than desirable results when dealing with complex geometry. By default, Solbri places a face count limit on the simplification process of complex geometry. Depending on how complex your geometry is, the result can cause your geometry to have missing faces or erode at its edges.

&nbsp;

The images below show an example of a rippled Wall. The rippled surface was first created in Grasshopper then imported into Revit as an in-place mass. Using the Wall by Face tool, a wall was hosted off of this highly rippled surface. After imported into SMC via IFC, the wall looked like it was a test surface for a dull hack saw. The window opening were not completely formed, the edges were ill-formed, and a lot of the wall had triangular holes.

&nbsp;

<a href="http://collectivebim.com/wp-content/uploads/2013/01/before.jpg"><img class="alignnone size-large wp-image-236" alt="before" src="http://collectivebim.com/wp-content/uploads/2013/01/before-840x465.jpg" width="840" height="465" /></a>

&nbsp;

&nbsp;

If your geometry consists of highly warped surfaces, an extreme amount of perforations, or dense ripples that require a very precise approximation, then you may need to tell Solibri to increase the face count of its geometry simplification process.

&nbsp;

This can be done by editing the vmoptions file located in Program Files\Solibri\SMCv8\Solibri Model Checker using Notepad. Add the following on a new line at the end of the document:
<pre>-Dsimplify-geometry-count=10000000</pre>
&nbsp;

Save the vmoptions file and restart Solibri. For the setting to take affect, you will have to re-import the geometry back into the model. You may notice a little hit in performance, but on the flip side you gain a more accurate representation of your complex geometry without distortion.

&nbsp;

The images below show the result of editing the vmoptions file.

<a href="http://collectivebim.com/wp-content/uploads/2013/01/after.jpg"><img class="alignnone size-large wp-image-237" alt="after" src="http://collectivebim.com/wp-content/uploads/2013/01/after-840x463.jpg" width="840" height="463" /></a>

&nbsp;
