---
layout: post
title: Grasshopper & Revit Interoperability: Adaptive Components via Hummingbird / Whitefeet
date: 2013-04-22 21:47
author: michael
comments: true
categories: [Grasshopper, Hummingbird, Interoperability, Revit, Whitefeet]
---
&nbsp;

<img class="size-full wp-image-382 aligncenter" alt="hummingbirds" src="http://collectivebim.com/wp-content/uploads/2013/04/hummingbirds3across.png" width="480" height="160" />

Now that we <span style="font-size: 13px;">have tested out </span><a style="font-size: 13px;" href="http://www.hilojacobs.com/?page_id=464" target="_blank">Chameleon</a><span style="font-size: 13px;"> in the </span><a style="font-size: 13px;" href="http://collectivebim.com/grasshopper-revit-interoperability-chameleon/" target="_blank">last post</a><span style="font-size: 13px;">, lets look at how </span><a style="font-size: 13px;" href="http://ghhummingbird.wordpress.com/" target="_blank">Hummingbird</a><span style="font-size: 13px;"> works. To be fair, I am going to use the same data set from Grasshopper and place the same Adaptive Component.</span>

&nbsp;

&nbsp;
<h3>About Hummingbird:</h3>
Hummingbird is a set of components, a plugin, for Grasshopper created by Tim Meador. The set includes components for creating datums like Levels and Grids, placing/drawing both loadable and system families, and includes geometry creation methods like lofting. Below are the required inputs to place an Adaptive Component. In comparison to Chameleon, it requires an additional four inputs which are mainly used to locate the Excel file, define the Tab in Excel, and reference an Adaptive Component already loaded into the Revit project. With Excel open, you just need to set the toggle to True to write the data to excel.

&nbsp;

<img class="wp-image-342 alignnone" style="font-size: 13px;" alt="Hummingbird_GH" src="http://collectivebim.com/wp-content/uploads/2013/04/Hummingbird_GH.jpg" width="178" height="362" /><img class="wp-image-348 alignright" alt="Hummingbird_GH2" src="http://collectivebim.com/wp-content/uploads/2013/04/Hummingbird_GH2.jpg" width="493" height="351" />

&nbsp;

&nbsp;

All the components write data in a pseudo-language to an Excel document. Every data branch in Grasshopper is written as a Row in Excel. Additional rows are created for defining the Revit command like setting the Adaptive Component, editing a parameter of a family, etc. This pseudo-language is then interpreted by the <a href="http://www.whitefeet.com/" target="_blank">Whitefeet </a>Revit Add-in.
<p style="text-align: center;"><img class=" wp-image-341 aligncenter" alt="Hummingbird_Excel" src="http://collectivebim.com/wp-content/uploads/2013/04/Hummingbird_Excel.jpg" width="986" height="431" /></p>
&nbsp;

&nbsp;
<h3>About Whitefeet:</h3>
The <a href="http://www.whitefeet.com/" target="_blank">Whitefeet</a> add-in is developed by Mario Guttman. There are a number of very powerful tools that are generally independent and address a very specific need, but one of these tools is the "Model Builder." The Model Builder was developed to import and export Revit elements in a way that allows geometry exchange with other programs. One of these programs is Rhino/Grasshopper via Excel. For more information on the tools, check out <a href="http://whitefeettools.wordpress.com/" target="_blank">Mario's blog</a>.

<img class="wp-image-343 alignleft" style="font-size: 13px;" alt="Hummingbird_Model Builder" src="http://collectivebim.com/wp-content/uploads/2013/04/Hummingbird_Model-Builder.jpg" width="294" height="327" />

<img class="wp-image-358 alignnone" style="font-size: 13px;" alt="modelbuilderdiagram" src="http://collectivebim.com/wp-content/uploads/2013/04/modelbuilderdiagram.jpg" width="460" height="352" />

&nbsp;
<h3></h3>
&nbsp;
<h3>Grasshopper to Revit Workflow: Placing Adaptive Components</h3>
Using the same [button link="http://collectivebim.com/wp-content/uploads/2013/04/Hummingbird.gh" color="#AAAAAA" size="1" style="1" dark="0" radius="auto" target="self"]Grasshopper Definition[/button] used for testing the <a title="Grasshopper &amp; Revit Interoperability: Adaptive Components via Chameleon" href="http://collectivebim.com/grasshopper-revit-interoperability-chameleon/" target="_blank">Chameleon workflow</a>, the Hummingbird Adaptive Component component is activated to write to the [button link="http://collectivebim.com/wp-content/uploads/2013/04/Hummingbird.xlsx" color="#AAAAAA" size="1" style="1" dark="0" radius="auto" target="self"]Excel File[/button]

&nbsp;
<h3><img class="wp-image-356 aligncenter" style="font-size: 13px; text-align: center;" alt="Hummingbird_GH3" src="http://collectivebim.com/wp-content/uploads/2013/04/Hummingbird_GH3.jpg" width="1101" height="347" /></h3>
&nbsp;

&nbsp;

&nbsp;

Line by line each Adaptive Component, its Element ID, and Adaptive Point locations are written in Excel on the specified Tab name.

<img class="alignnone size-large wp-image-357" alt="Hummingbird_Excel2" src="http://collectivebim.com/wp-content/uploads/2013/04/Hummingbird_Excel2-840x209.jpg" width="840" height="209" />

&nbsp;

&nbsp;

Once the Excel document is saved, you then open up Whitefeet's Model Builder.

<img alt="Hummingbird_Model Builder" src="http://collectivebim.com/wp-content/uploads/2013/04/Hummingbird_Model-Builder.jpg" width="294" height="327" />

&nbsp;

&nbsp;

In the Model Builder window, you first select "Import Excel to Elements".

<img class="alignnone size-full wp-image-344" style="font-size: 13px;" alt="Hummingbird_Model Builder2" src="http://collectivebim.com/wp-content/uploads/2013/04/Hummingbird_Model-Builder2.jpg" width="818" height="352" />

&nbsp;

&nbsp;

Then navigate to the location of the Excel file. The Model Builder will quickly look at the Sheets available in the Excel document to allow you to choose which sheet you want to build. You then select which "Mode" to build in. From the three you can select from, it appears that none of them allow you to update an already placed element, but rather
<ol>
	<li><span style="font-size: 13px;">add all new leaving the already placed in the document to be manually deleted if </span>necessary</li>
	<li>leave existing elements that match and only add new elements</li>
	<li>or delete existing elements that match and make all new elements.</li>
</ol>
Next you need to select the Adaptive Component family you want to place. The one thing that is confusing here is that we have already defined the Adaptive Component name in the Grasshopper file and Excel file, but now we have an option to define it here? It turns out that since we defined the Adaptive Component in Grasshopper, it does not matter what we select here.

<img class="alignnone size-full wp-image-345" alt="Hummingbird_Model Builder3" src="http://collectivebim.com/wp-content/uploads/2013/04/Hummingbird_Model-Builder3.jpg" width="783" height="655" />

&nbsp;

&nbsp;

Once you click "Process," your computer fan will kick in and after a few seconds of nothing happening, a progress bar finally appears. This process takes a long time as it parses through each row of the excel file.

<img class="alignnone size-full wp-image-347" style="font-size: 13px;" alt="Hummingbird_Model Builder5" src="http://collectivebim.com/wp-content/uploads/2013/04/Hummingbird_Model-Builder5.jpg" width="791" height="55" />

&nbsp;

&nbsp;

When the Adaptive Components finish being instantiated, you will notice that the Undo stack is littered with each family placement. This could be problematic if you are placing 1000's of components and selecting them individually to delete them may be impossible.
<p style="text-align: center;"><img class=" wp-image-346 aligncenter" style="font-size: 13px;" alt="Hummingbird_Model Builder4" src="http://collectivebim.com/wp-content/uploads/2013/04/Hummingbird_Model-Builder4.jpg" width="138" height="455" /></p>
&nbsp;

&nbsp;

When using the same data set as the previous post, I ran into an issue with the Hummingbird/Whitefeet workflow. After talking with Tim and Mario, it was suggested that it may be an issue with the Model Builder where it has trouble sometimes making Extrusions in an Adaptive Component. This issue turned out to not be that issue, but one even simpler. In the previous data set I was sequencing the points a little weird in the first place, it just somehow worked with Chameleon. If you were to step around the surface, the adaptive points were sequenced as so, 1-2-4-3. With Hummingbird/Whitefeet I had to sequence it as so, 1-2-3-4. Though it makes sense, I would think that it should not matter what order you place the points of an Adaptive Component as long as it aligns with the shape grammer. I think this actually makes a good test case. Here is the revised [button link="http://collectivebim.com/wp-content/uploads/2013/04/4_Pt_Plane_02.rfa" color="#AAAAAA" size="1" style="1" dark="0" radius="auto" target="self"]Adaptive Component[/button].

&nbsp;

<img class="wp-image-351 alignleft" alt="Hummingbird_Revit_Adpt_Placed3" src="http://collectivebim.com/wp-content/uploads/2013/04/Hummingbird_Revit_Adpt_Placed3.jpg" width="355" height="222" /> <img class="wp-image-350 alignleft" alt="Hummingbird_Revit_Adpt_Placed2" src="http://collectivebim.com/wp-content/uploads/2013/04/Hummingbird_Revit_Adpt_Placed2.jpg" width="371" height="222" />

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

&nbsp;

My comments for this workflow, for what it is worth, is that it is a robust way to automate the placement of Revit families from Grasshopper. There are components in this tool set that is not available in any of the other workflows available. The ones I am thinking of are the Lines, Rooms, Masses, &amp; Topos. In addition, once you get your feet wet with the Whitefeet tools, you will notice how much you can do with just those tools in Revit. On the Grasshopper side, you will find that most of the other components can be handled better through the Case tools or through Geometry Gym. It is also nice that it has an integration with other tools with the possibilities of others in the future.

This issues I have with the workflow primarily focuses around speed. With Excel being the intermediary platform, it takes an unnecessary amount of time to write the data to Excel just to turn around and take longer to process it. As you will notice, the more elements/rows you have in the excel document, the processing time grows enormously. Another issue I have with it just as with Chameleon, is that updating existing elements without deleting them and rebuilding is not possible.
