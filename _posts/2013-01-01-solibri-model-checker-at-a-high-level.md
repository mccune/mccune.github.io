---
layout: post
title: Solibri Model Checker at a high level.
date: 2013-01-01 00:01
author: michael
comments: true
categories: [Analysis, BIM, Coordination, IFC, Solibri]
---
&nbsp;

<a href="http://www.solibri.com/solibri-model-checker.html">Solibri Model Checker</a> is not an authoring tool, but merely an awesome "model checker". Like <a href="http://usa.autodesk.com/navisworks/">Navisworks</a> it does clash detection and model comparing, but unlike Navisworks it takes advantage of the information embedded within the building information models for more than just clash detection. As an architect and now a BIM specialist, there are things that Solibri Model Checker can check for, if set up properly, that is invaluable for a firm that participates in BIM.

&nbsp;
<h3><a href="http://collectivebim.com/wp-content/uploads/2013/01/SMC-Overview.jpg"><img class="alignnone size-large wp-image-229" alt="SMC Overview" src="http://collectivebim.com/wp-content/uploads/2013/01/SMC-Overview-840x484.jpg" width="840" height="484" /></a></h3>
&nbsp;

[divider top="1"]
<h3>Importing into SMC</h3>
<a href="http://www.solibri.com/solibri-model-checker.html">Solibri Model Checker</a> only opens models from a IFC or DWG format. The IFC format is the preferred method as I have tested out the DWG from Revit and it is inconsistent. For example, if you export as a polymesh it maps the elements to the correct IFC type, but object is made up of single unjoined surfaces. Exporting as an ACIS Solid keeps the object's faces together, but some objects don't get categorized to the correct IFC type and instead ends up in the "object" type.

&nbsp;

Importing an IFC does a great job, but you have to make sure that you are mapping your elements to the correct IFC category in Revit's Export IFC Options table.  By default, <a href="http://usa.autodesk.com/revit/">Revit</a> does not have the correct Revit categories mapped to the correct IfcType. For example, Revit has general categories like "Mechanical Equipment" and IFC is a bit more specific  like IfcChiller, IfcCondenserType, and IfcPumpType.

&nbsp;

If you need to map a custom element to the correct IFC type, then there are two options.
<ol>
<ol>
	<li>Define a subcategory under Mechanical Equipment when creating the "chiller" family, and in the Revit IFC export options you can map that subcategory to the right IFC category.</li>
	<li>Create two shared parameters inside the families that need to be mapped correctly to specific IFC Types.</li>
</ol>
</ol>
There are a few Revit Addins out there that imporve <a href="http://apps.exchange.autodesk.com/RVT/Detail/Index?id=appstore.exchange.autodesk.com%3Aifcexporterforrevit%3Aen">Revit's IFC Export</a>. I will be sure to cover those in a separate post as that subject matter can be an entire post on its own.

&nbsp;

&nbsp;

[divider top="1"]
<h3>Exporting from Revit</h3>
In my specific test, when I exported from <a href="http://usa.autodesk.com/revit/">Revit</a> a 250+ MB architectural model, it took 45-60 mins using the <a href="http://usa.autodesk.com/adsk/servlet/pc/item?id=13947462&amp;siteID=123112">Navisworks Exporter Add-in</a>. When I exported an .ifc file, it took 10 mins. Structural and Mechanical models took less than 2 minutes. For models that that had a great deal of complex geometry not native to Revit, the export took 30-45 min as an .nwc, but literally 1-2 hours to export as an .ifc. Additionally, it took 1-2 hours to import into SMC.

&nbsp;

[divider top="1"]
<h3>Model Structure</h3>
When imported into Solibri Model Checker, there are three ways to view the structure of the data in the Model Tree.

&nbsp;

<strong>Containment Hierarchy</strong>- Displays elements by Model (given a discipline), then by Level, then by IFC Object Type, then by Family Name, then by Item.

<a href="http://collectivebim.com/wp-content/uploads/2012/12/SMC-Containment-Hierarchy.jpg"><img class="alignnone size-full wp-image-101" alt="SMC Containment Hierarchy" src="http://collectivebim.com/wp-content/uploads/2012/12/SMC-Containment-Hierarchy.jpg" width="599" height="816" /></a>

&nbsp;

<strong>Component Hierarchy</strong> - Displays elements by IFC Object Type, then Family Name, then Item.

<a href="http://collectivebim.com/wp-content/uploads/2012/12/SMC-Component-Hierarchy.jpg"><img class="alignnone size-full wp-image-100" alt="SMC Component Hierarchy" src="http://collectivebim.com/wp-content/uploads/2012/12/SMC-Component-Hierarchy.jpg" width="598" height="818" /></a>

&nbsp;

<strong>Layer Hierarchy</strong> - Displays elements by Layer, then by IFC Object Type, then by Item. One issue noticed with this view is that <a href="http://www.solibri.com/solibri-model-checker.html">Solibri Model Checker</a> does not merge similar layers of different models into the same folder. This may be a bug in the current version though.

<a href="http://collectivebim.com/wp-content/uploads/2012/12/SMC-Layer-Hierarchy.jpg"><img class="alignnone size-full wp-image-105" alt="SMC Layer Hierarchy" src="http://collectivebim.com/wp-content/uploads/2012/12/SMC-Layer-Hierarchy.jpg" width="599" height="819" /></a>

&nbsp;

&nbsp;

[divider top="1"]
<h3>Element Properties</h3>
In addition to the lack of knowledge out there, I think the slow adoption of Solibri Model Checker within the US is mainly due to the nuances encountered when mapping to IFC.  I want to encourage you to look beyond that because you can still use Solibri Model Checker to its fullest even if your model does not translate over perfectly.  Just like how Navisworks selects what it needs to clash via "Search Sets and Selection Sets", Solibri Model Checker has the same capability to define its own "Search Sets" but they are called Classifications.

&nbsp;

<a href="http://www.solibri.com/solibri-model-checker.html">Solibri Model Checker</a> Classifications are defined just like how <a href="http://usa.autodesk.com/navisworks/">Navisworks</a> defines Search Sets, by selecting by specific objects properties.

<a href="http://collectivebim.com/wp-content/uploads/2012/12/SMC-Info-Panel.jpg"><img class="alignnone size-full wp-image-102" alt="SMC Info Panel" src="http://collectivebim.com/wp-content/uploads/2012/12/SMC-Info-Panel.jpg" width="460" height="404" /></a>

&nbsp;

&nbsp;

[divider top="1"]
<h3>Classification</h3>
When setting up custom Classifications, which is easier than setting up search sets in <a href="http://usa.autodesk.com/navisworks/">Navisworks</a>, <a href="http://www.solibri.com/solibri-model-checker.html">Solibri Model Checker</a> gives you a list of elements that were and were not Classified by your filter rules. Examples of Classification that you would create are like the following:

<a href="http://collectivebim.com/wp-content/uploads/2012/12/SMC-Classification-Panel.jpg"><img class="alignnone size-full wp-image-99" alt="SMC Classification Panel" src="http://collectivebim.com/wp-content/uploads/2012/12/SMC-Classification-Panel.jpg" width="458" height="334" /></a>

&nbsp;

&nbsp;

[divider top="1"]
<h3>Model Checking - Rules</h3>
<a href="http://www.solibri.com/solibri-model-checker.html">Solibri Model Checker</a> then uses Rulesets to check for things. Some Rulesets allow you to select by Component (IFC) while others allow you to select only by Classification. There are even some that allow you to put both together. This inconsistency is being address by Solibri as they are continuously updating the Rulesets.

<img class="alignnone size-full wp-image-108" alt="SMC Rulesets" src="http://collectivebim.com/wp-content/uploads/2012/12/SMC-Rulesets.png" width="533" height="907" />

&nbsp;

These Rulesets are what set Solibri Model Checker apart from any other model aggregator on the market. Once the Classifications are set up correctly, you can use the rulesets for Clash Detection, Quality Assurance, Model Craft, Missing Parameters, Naming Conventions, Building Logistics, Code Compliance, and even Validation of Design Ideas.

&nbsp;

&nbsp;

[divider top="1"]
<h3>Model Checking - Parameters</h3>
The Rulesets have very specific parameters built in that are very flexible for many different scenarios. The Ruleset Parameters below are for checking for elements within a door swing and for egress analysis.

<img class="alignnone size-full wp-image-114" alt="SMC Ruleset Parameters" src="http://collectivebim.com/wp-content/uploads/2012/12/SMC-Ruleset-Parameters.png" width="768" height="472" />

<a href="http://collectivebim.com/wp-content/uploads/2012/12/SMC-Ruleset-Parameters-2.png"><img class="alignnone size-full wp-image-113" alt="SMC Ruleset Parameters 2" src="http://collectivebim.com/wp-content/uploads/2012/12/SMC-Ruleset-Parameters-2.png" width="753" height="885" /></a>

&nbsp;

[divider top="1"]
<h3>Results - Annotating</h3>
Using the Door swing as an example, <a href="http://www.solibri.com/solibri-model-checker.html">Solibri Model Checker</a> takes longer with finding issues than <a href="http://usa.autodesk.com/navisworks/">Navisworks</a>, but Solibri Model Checker is isolating the elements involved with the issue AND annotating it. The objects that are within the required area in front of the door are projected down onto a plane and Solibri Model Checker strikes dimensions to both elements from the door. You will notice that just because you only have 3 elements showing, your orientation in the building is not lost like in Navisworks. Solibri Model Checker slices the model at the building levels and gives you a line drawing of every floor. It also labels all Areas/Rooms and Grids. You can then add your own annotations in 3d space.

<a href="http://collectivebim.com/wp-content/uploads/2013/01/SMC-01.jpg"><img class="alignnone size-large wp-image-230" alt="SMC 01" src="http://collectivebim.com/wp-content/uploads/2013/01/SMC-01-840x550.jpg" width="840" height="550" /></a>

When you are ready to save the issue, you create a slide which saves your orientation of the model, hidden elements, and added annotations.

<a href="http://collectivebim.com/wp-content/uploads/2012/12/SMC-Results.jpg"><img class="alignnone size-full wp-image-107" alt="SMC Results" src="http://collectivebim.com/wp-content/uploads/2012/12/SMC-Results.jpg" width="424" height="269" /></a>

&nbsp;

&nbsp;

[divider top="1"]
<h3>Results - Tracking</h3>
The slide has properties of its own as it can track Decisions, Comments, Locations, Date slide created, Status, and Responsibilities.

<a href="http://collectivebim.com/wp-content/uploads/2013/01/SMC-Issue-Details.jpg"><img class="alignnone size-full wp-image-232" alt="SMC Issue Details" src="http://collectivebim.com/wp-content/uploads/2013/01/SMC-Issue-Details.jpg" width="404" height="584" /></a> <img class="alignnone size-full wp-image-103" alt="SMC Issue Details 02" src="http://collectivebim.com/wp-content/uploads/2012/12/SMC-Issue-Details-02.jpg" width="406" height="590" />

&nbsp;

&nbsp;

[divider top="1"]
<h3>Results - Presenting</h3>
These slides can then be added to a "Presentation" and you can play through the slides like a slide show.

<a href="http://collectivebim.com/wp-content/uploads/2013/01/SMC-Presentation.jpg"><img class="alignnone size-full wp-image-231" alt="SMC Presentation" src="http://collectivebim.com/wp-content/uploads/2013/01/SMC-Presentation.jpg" width="396" height="929" /></a>

&nbsp;

[divider top="1"]
<h3>Results - Reporting</h3>
This Presentation can then be reported out as a pdf and csv doc with customizable templates.

In addition to the rulesets, you can also do an Information Takeoff and Report it.

<a href="http://collectivebim.com/wp-content/uploads/2013/01/SMC-Report.jpg"><img class="alignnone size-full wp-image-234" alt="SMC Report" src="http://collectivebim.com/wp-content/uploads/2013/01/SMC-Report.jpg" width="751" height="605" /></a>

&nbsp;

[divider top="1"]
<h3>Solibri Model Viewer</h3>
The checked <a href="http://www.solibri.com/solibri-model-checker.html">Solibri Model Checker</a> model can be saved as an .smc and opened by the free Solibri Model Viewer. The Model Viewer does not give you access to the Rulesets or Ruleset Parameters, but maintains the ability to review Check Results, Takeoffs, Presentations, Slides, and Annotations.

&nbsp;

&nbsp;

[divider top="1"]
<h3>Limitations</h3>
Current limitations found in Solibri Model Checker:
<ul>
	<li>Inability to add slides to an existing presentation.</li>
	<li>Inability to add the "newest" created slides to a new presentation.</li>
	<li>Inability to have a user categorization of results.</li>
	<li>Solibri Model Checker automatically creates folders for you based off of things unknown to the user. Most of the time it is the levels of the objects that are in the first column of "checked components".</li>
	<li>Would be nice to completely reorganize the results more like the way <a href="http://usa.autodesk.com/navisworks/">Navisworks</a> works.</li>
	<li>Inability to add a single slide to multiple issues/results. So grouping 5 issues and using 1 slide to tie them all together.</li>
	<li>Inability to group the ITO so that the scrolling is not tremendously long.</li>
	<li>Inability to add custom fields to Slides that can be reported out.</li>
	<li>Currently the location is available in the Slide and can be reported out, but it would be nice to have the "types" of elements involved in the clash so that ultimately you could report out that this issue involves "doors, light fixtures, etc"</li>
</ul>
