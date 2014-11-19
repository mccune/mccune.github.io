---
layout: post
title: Grasshopper & Revit Interoperability - CASE workflow tools
date: 2013-05-02 17:49
author: michael
comments: true
categories: [CASE, Grasshopper, Interoperability, Revit, Rhino]
---
<img class="size-full wp-image-810 aligncenter" alt="CASE LOGOS" src="/images/2013/05/CASE-LOGO.jpg" width="500" height="168" />
<h2>About the CASE workflow tools:</h2>
The last of these interopability tools that I will cover will be one of our own.  All of the tools previously mentioned are great and currently serve a real need in the industry<em> (post to follow comparing them all side by side)</em>. We actually have used or currently use most of them in our everyday operations; however, being that we are capable of building our own tools we found the need to build scalable and extendable solutions for our clients. We are extremely excited about the development of these new tools and in fact, they are so new that a name for them has not been decided upon yet. For now, I will refer to them as the CASE workflow tools. You may have even seen some teaser images or videos done on the amazing <strong><a href="http://www.case-inc.com/users/nmiller">Nate Miller</a></strong>'s <strong><a href="http://www.theprovingground.org/">blog</a></strong>, who is the lead developer of these tools.  How are these tools any different you say?

&nbsp;

<strong>Coordinated information across a team:</strong>

The CASE workflow tools tackle the issue of managing geometry changes across different platforms across different teams. It is common that the team building a definition in Grasshopper is not always the same team managing the Revit model. Through a web service, the CASE workflow tools compensate for this project structure by allowing the information to be accessible to a team and not just to one person. No more boring files to search through to find the correct one! Updating models become managed, controlled, fast, and easy as pie.

&nbsp;

<strong>Learning Curve:</strong>

The is no learning curve for these tools,<em> if you know Grasshopper already :)</em>. The User Interface has been designed to eliminate as many useless inputs and user errors as possible and it will continue to improve. The conversion of units is handled for you, allowing you to work "unitless" in Rhino and define your units for exporting to Revit.

&nbsp;

<strong>Streamlined Model Updates:</strong>

We know that deleting all or selectively deleting can be a pain. So we reduced and, when possible, eliminated the need for manual deleting prior to updating. This also allows for selective parameter changes of elements without the need to run the entire batch.

&nbsp;

<strong>Professional Development, Implementation, and Support:</strong>

The one thing you may have guessed is that these tools are not free. This is actually a really good thing as it means we are actively developing it. We also understand that these types of workflows vary across the board and can require some expertise to design the workflow. So in addition to actively developing it alongside you, we also implement it into the project, train the team, and support the progress. We are actively working with with firms to consult on projects and deploy these tools.  Feel free to contact us if you are interested in collaborating!  <a href="http://www.case-inc.com/contact" target="_blank"><b>http://www.case-inc.com/contact</b></a>

&nbsp;

[divider top="1"]
<h3></h3>
<h3>CASE Tools: Grasshopper and Revit</h3>
The CASE tools currently consist of a series of Grasshopper Components and a Revit Add-in.

&nbsp;

<strong>GH - Interop tab:</strong>

The Interop tab contains workflow components for creating Revit specific elements.

<img class="size-full wp-image-824 aligncenter" alt="CASE_Grasshopper Tools 012" src="/images/2013/05/CASE_Grasshopper-Tools-012.jpg" width="143" height="296" />

<strong>Revit - CASE Design, Inc. tab</strong>

On the Revit side of things, there  is only one component that does all the magic, the "CASE Exchange."

<img class="size-full wp-image-819 aligncenter" alt="CASE_Grasshopper Tools 07" src="/images/2013/05/CASE_Grasshopper-Tools-07.jpg" width="431" height="120" />

&nbsp;

&nbsp;

[divider top="1"]
<h3></h3>
<h3>Grasshopper to Revit Workflow: Placing Adaptive Components</h3>
Using the same Grasshopper Definition and [button link="/images/2013/04/4_Pt_Plane_02.rfa" color="#AAAAAA" size="1" style="1" dark="0" radius="auto" target="self"]Adaptive Component[/button], I will walk through the steps using the CASE workflow tools.

&nbsp;

The Adaptive Component component in Grasshopper has only two inputs, a Boolean toggle to execute the export and the points for the Adaptive Component's adaptive points.

<img class="size-full wp-image-813 aligncenter" alt="CASE_Grasshopper Tools 01" src="/images/2013/05/CASE_Grasshopper-Tools-01.jpg" width="553" height="307" />

&nbsp;

Before you set the toggle to TRUE, you first have to define some settings by right-clicking on the component.

<img class="size-full wp-image-814 aligncenter" alt="CASE_Grasshopper Tools 02" src="/images/2013/05/CASE_Grasshopper-Tools-02.jpg" width="333" height="199" />

&nbsp;

The Login Settings will bring up a window to define the credentials for the web service.

<img class="size-full wp-image-815 aligncenter" alt="CASE_Grasshopper Tools 03" src="/images/2013/05/CASE_Grasshopper-Tools-03.jpg" width="370" height="304" />

&nbsp;

The Data Settings will bring up a window to define a Data ID <em>(file name)</em>, the Units to export as, the Category of the Adaptive Component family, and the Adaptive Component's Family and Type name.

<img class="size-full wp-image-816 aligncenter" alt="CASE_Grasshopper Tools 04" src="/images/2013/05/CASE_Grasshopper-Tools-04.jpg" width="454" height="320" /><img class="size-full wp-image-817 aligncenter" alt="CASE_Grasshopper Tools 05" src="/images/2013/05/CASE_Grasshopper-Tools-05.jpg" width="454" height="320" />

&nbsp;

Once you save all the settings and set the toggle to TRUE, the component will sync your data to the web.

<img class="size-full wp-image-818 aligncenter" alt="CASE_Grasshopper Tools 06" src="/images/2013/05/CASE_Grasshopper-Tools-06.jpg" width="454" height="100" />

&nbsp;

Then once you click the Addin in Revit, the same window pops up to enter your credentials. This could be a different person on the team, but for now it is just me again. You also only have to enter your credentials the first time and check "Remember Me."

<img class="size-full wp-image-820 aligncenter" alt="CASE_Grasshopper Tools 08" src="/images/2013/05/CASE_Grasshopper-Tools-08.jpg" width="370" height="338" />

&nbsp;

When you Login it will access the web service and allow you to choose which file you would like to sync.

<img class="size-full wp-image-821 aligncenter" alt="CASE_Grasshopper Tools 09" src="/images/2013/05/CASE_Grasshopper-Tools-09.jpg" width="370" height="338" />

&nbsp;

Select which file you want to sync and then decide if you want to "Update" previously placed elements or "Replace" to create entirely new ones!

<img class="size-full wp-image-831 aligncenter" alt="CASE_Grasshopper Tools 010" src="/images/2013/05/CASE_Grasshopper-Tools-0101.jpg" width="370" height="440" />

&nbsp;
<p style="text-align: center;"><img class=" wp-image-468 aligncenter" alt="" src="/images/2013/04/Geometry-Gym-Placed-1.jpg" width="698" height="607" /></p>
[divider top="1"]
<h3>Workshops around these tools:</h3>
For an additional write up about these tools and their recent deployments at a few workshops, check out <a href="http://www.theprovingground.org/2013/05/spring-workshop-recap-parametric.html" target="_blank">Nate's blog post</a>.

[divider top="1"]
<h3>Some videos previewing the tools:</h3>
&nbsp;

[responsive_youtube XP-oDq1NNMg]

&nbsp;

[responsive_youtube yKcpQGVGn3I]

&nbsp;

[responsive_youtube FvY5r_sA1KI]
