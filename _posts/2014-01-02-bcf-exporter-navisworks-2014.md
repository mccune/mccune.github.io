---
layout: post
title: BCF Exporter for Navisworks 2014
date: 2014-01-02 22:57
author: michael
comments: true
categories: [Analysis, BCF, BIM, CASE, Coordination, Interoperability, Navisworks]
---
<p style="text-align: center;"><img class="size-full wp-image-1205 aligncenter" alt="Navisworks BCF Exporter" src="http://collectivebim.com/wp-content/uploads/2014/01/Navisworks-BCF-Exporter.png" width="160" height="160" /></p>
At CASE, we often use Navisworks in addition to Solibri Model Checker. If you use either of these tools, you are aware that they are primarily analysis tools used for coordination and quality control. The primary output of these two tools for coordination are in the form of reports. Navisworks can report clashes in the form of TXT, HTML, and XML. Solibri Model Checker is capable of reporting issues as PDF, XLS, RTF, and BCF. Of all of these formats between the two software, BCF is the only format that contains a camera view. A camera view is crucial to pinpointing an issue inside a model. Trying to find the same location from an image is extremely time consuming. What is missing from this picture? A BCF Exporter for Navisworks!

&nbsp;

So with the assistance of <a href="http://matteocominetti.com/" target="_blank">Matteo's </a>crazy ninja programming skills, we developed a <a href="https://aec-apps.com/app/app/bcf-exporter-navisworks" target="_blank">FREE Navisworks Manage 2014 Add-in</a> that allows users to export viewpoints as a BCF! With this, you can share the issues you find in Navisworks Manage with people that are Solibri and Tekla BIMsight. With the <a href="http://www.kubusinfo.com/en/What-is-BCF" target="_blank">PAID Kubus' BCF Add-in</a>, you can review the issues in ArchiCAD and Revit. You can also review the issues in Revit with<a href="https://aec-apps.com/app/app/bcf-plugin-2-revit" target="_blank"> Matteo's FREE Revit BCF addin</a>! See what I mean about his crazy ninja skills?

&nbsp;

The workflow is simple. You can either create the viewpoints manually from any camera position, or you can generate the viewpoints as a report of a clash detection test. Since the BCF schema does not support multiple images per issue, the Add-in flattens any folder structure you have in the viewpoints window and treats each viewpoint as a potential issue. A great feature of Navisworks that is often under utilized is the comments feature. Comments added to clash results will be attached to a viewpoint if reported from the clash detective. Additionally, if a viewpoint was created manually, a comment can be added to the viewpoint after the fact by right clicking on the viewpoint in the viewpoint window.

&nbsp;

Before using the tool to export a BCF, be sure to set your desired image size for the snapshot. If you don't, the image will be 256 x 256. To change the image size, you have to enter the Advanced Global Options by Shift+Clicking the Global Options from either the Navisworks icon menu or by right clicking in the scene. Under Export, you will find "lcodpimage." Change the height and width to the desired size.

&nbsp;

When you run the Add-in, a window will appear that displays all the viewpoints in your model. Select which viewpoints you DO NOT want to export and remove them from the list with the button at the top. After clicking the Export Issues button and specifying a file name, the Add-in will cycle through all the viewpoints and capture the camera position, a snapshot, any comments associated with the viewpoint, and the GUIDs of all objects visible in the scene.

&nbsp;

The video below walks through a few workflows for using the tool. To install this tool, please use the CASE Add-in manager that can be found here: <a href="http://apps.case-inc.com/content/add-manager" target="_blank">http://apps.case-inc.com/content/add-manager</a>. While you are there, check out all the other FREE Add-ins we give away.

&nbsp;

[responsive_vid]
