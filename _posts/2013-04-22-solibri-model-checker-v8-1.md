---
layout: post
title: Solibri Model Checker v8.1 released
date: 2013-04-22 23:19
author: michael
comments: true
categories: [Analysis, BIM, Coordination, IFC, SMC, Solibri]
---
&nbsp;

<em>From Solibri's Press Release:</em>

&nbsp;

<span style="font-size: 13px;">[quote style="1"]</span>Solibri Introduces Solibri Model Checker v8.1 improving user experience, information access and visualization, while implementing key R&amp;D requests from customers.

&nbsp;

This release emphasizes:
<ul>
	<li>usability and user experience</li>
	<li>availability and accessibility of BIM data and visual information</li>
	<li>strong customer focus</li>
</ul>
<div></div>
<div></div>
&nbsp;
<h2>Usability and User Experience</h2>
“SMC has always received praise for user friendliness. This has also been one of the key themes in all recent releases. For example, our previous version (SMC v8) included guided step-by-step instructions for carrying out even the most difficult BIM QA/QC tasks, enabling any user to realize the full business benefits from SMC” states Mr. Heikki Kulusjärvi, CEO of Solibri, Inc.

SMC v8.1 perfects many of the tasks from the end-user point of view. The overall user experience has improved significantly and visualization speed has increased dramatically, making QA/QC more efficient. BIM collaboration and communication, as well as mark-up functionality have been greatly improved: Also, the core of SMC, the automated rule-based model checking and related step-by-step task customization has new capabilities for ensuring better QA/QC results.

&nbsp;

&nbsp;
<h2>Strong Customer Focus</h2>
“Solibri Model Checker v8.1 also addresses development requests provided by our most advanced and BIM savvy customers. We greatly appreciate this input since it enables us to remain at the leading edge of BIM QA/QC. Close co-operation with the global user base enables us to serve the market while continuously improving our offering, and providing increased value to our customers“ Mr. Kulusjärvi continues.[/quote]

&nbsp;

[divider top="0"]

&nbsp;

Lets get down to the details about what has been updated! There has been a lot of changes and great improvements in this release and I look forward to sharing some of them in future posts.

&nbsp;

<em>Below is from Solibri's website.</em>

[quote style="1"]
<h2>Support for new Excel (.xlsx) format</h2>
<ul>
	<li>Data can now be imported from .xlsx files</li>
	<li>Reports can be done in the .xlsx format. Reports that use templates are in the new format when the template is also in the new format.</li>
</ul>
&nbsp;
<h2>3D</h2>
<ul>
	<li>Improved performance</li>
	<li>Ortho View added</li>
	<li>Area selection and hiding</li>
	<li>Selection from 3D modified so that it always clears the selection basket, unless Ctrl-button is pressed down</li>
	<li>Contents of the component quick info window are configurable</li>
	<li>Section planes with outlines</li>
	<li>Section plane can be selected as markup plane</li>
	<li>Hide tool can be used to remove markups and dimensions</li>
	<li>Navigation map shows the name of the current floor. You can switch to another floor by clicking the name and choosing the new floor from the list.</li>
	<li>Minimum and maximum sizes of dimensions and footprint space info text can be set</li>
	<li>Showing and zooming to global origin</li>
	<li>Smoother colors and shading</li>
</ul>
&nbsp;
<h2>Classification</h2>
<ul>
	<li>Default classification names and colors can be listed in a separate table that can also be read to/from Excel file.</li>
	<li>Classification logic can now use either “Best Match” or the new “First Match” method. The latter evaluated the classification rules from top to bottom and the first row that matches a component is selected as the classification name. The Best Match method evaluates all rows and finds the best matching one.</li>
	<li>The source of classification is shown in the classification settings dialog’s classified components tab</li>
</ul>
&nbsp;
<h2>Compartmentation</h2>
<ul>
	<li>Possibility to use classifications in compartmentation wizard</li>
</ul>
&nbsp;
<h2>Result Summary</h2>
<ul>
	<li>Possibility to visualize results summary in 3D by severity colors so that component’s color is more solid the more issues it has.</li>
</ul>
&nbsp;
<h2>Tasks</h2>
<ul>
	<li>Classification task is now configurable. You can specify whether all components should be classified, or whether the user should verify the classification even in the case when enough components have been classified.</li>
	<li>User defined tasks related to a Ruleset can refer to a rule to provide better targeting of the task.</li>
</ul>
&nbsp;
<h2>Communication</h2>
<ul>
	<li>Link back to checking results and the checked rule from the issue in presentation available from popup menu.</li>
	<li>A new toolbar below the 3D window for easy management of  coordination information.</li>
	<li>More intuitive way  to navigate between slides in issues.</li>
	<li>All slides in issues are now reported in PDF and RTF reports.</li>
	<li>Issue id added to the PDF and RTF reports.</li>
</ul>
&nbsp;
<h2>Model Tree</h2>
<ul>
	<li>Relocating of models simplified. If you want to move several models with the same translation, you only need to give the value once. Also the translation can easily be measured from the models.</li>
</ul>
&nbsp;
<h2>Information Takeoff</h2>
<ul>
	<li>Possibility to add version number of Solibri Model Checker in the Excel reports made with template.</li>
</ul>
&nbsp;
<h2>Rule Updates</h2>
<ul>
	<li>#222: Possibility to check vertical distance between components.</li>
	<li>#179: More parameters (required by some building codes) and better explanations of route lengths.</li>
	<li>#11: Possibility to require either components from all rows, or only from one.</li>
	<li>#231: Possibility to check windows/doors/openings located in the same wall.</li>
	<li>#9, #11, #176 added possibility to select several disciplines instead of only one.</li>
</ul>
&nbsp;
<h2>Possibility to customize ITOs and hyperlinks with scripts (currently available only for selected Partners and customers)</h2>
<ul>
	<li>ITO column can have a script that calculates its value based on other columns. For example, a mass column could calculate its value on volume column</li>
	<li>Hyperlink view has a possibility to open hyperlink templates that automatically create hyperlinks based on component property values.</li>
</ul>
&nbsp;
<h2>Updated Rulesets</h2>
<ul>
	<li>Coverings (insulation) in MEP intersections
<ul>
	<li>Intersections without insulation (small tolerances)</li>
	<li>Intersections between ’hard material’ and insulation (’medium’ tolerances)</li>
	<li>Intersections between insulations (larger tolerances)</li>
</ul>
</li>
</ul>
<ul>
	<li>BIM Validation – Architectural
<ul>
	<li>Rule to check free space above suspended ceilings</li>
</ul>
</li>
</ul>
&nbsp;
<h2>IFC import</h2>
<ul>
	<li>Added more coverage of information relevant for COBie</li>
	<li>Better support for covering (e.g. insulation around pipes). Intersection between coverings can now be checked separately, if they are modeled separately in the IFC file.[/quote]</li>
</ul>
&nbsp;
