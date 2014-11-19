---
layout: post
title: Grasshopper & Revit Interoperability - Adaptive Components via Chameleon
date: 2013-04-17 21:46
author: michael
comments: true
categories: [Chameleon, Grasshopper, Interoperability, Revit, Rhino]
---
<p style="text-align: center;"><a href="http://www.hilojacobs.com/?page_id=464"><img class="size-full wp-image-294 aligncenter" alt="Chameleon_logo" src="/images/2013/04/Chameleon_logo2.jpg" width="147" height="148" /></a></p>
The need to operate between multiple design technologies is growing everyday. New apps are constantly arriving and it is sometimes hard to keep up. <a href="http://aec-apps.com/">AEC-APPS</a> <em>(plug)</em> helps out a lot, but communicating between different platforms is often a challenge usually resulting to importing geometry that cannot be edited except within its native format. In the next series of posts, I am going to elaborate a bit on what tools out there can help us operate between Rhino/Grasshopper and Revit. Honestly, they all do a great job with getting the information over. All of them use very different means to do it, and I am always impressed at how robust and accurate the results are. Since they all can place Adaptive Components, I will start there. I will go through each tool and elaborate a bit on what it takes to set it up, transfer it, as well as share the files to do it yourself. Note that some of the plugins that I will cover are either not free or not publicly available, so you may not be able to repeat the steps. The first tool will be <a href="http://www.hilojacobs.com/?page_id=464">Chameleon</a>.

&nbsp;
<h3>About Chameleon:</h3>
<a href="http://www.hilojacobs.com/?page_id=464">Chameleon </a>is both a plugin for Grasshopper and an Add-in for Revit. Developed by Hiroshi Jacobs, a lot of its roots grew out of his work at the GSD at Harvard especially the Curtain Grid tools. Since the GSD, the app has grown to include a workflow between Grasshopper and Revit using gbxml. Knowing Hiroshi personally, his aim for the tools as they continue to expand is to make it as approachable and streamlined as it can be. Making it easier for non-techie designers to pick up the tool and get what they want done. The workflow, as you will see with the Adaptive Components, makes it to where you do not have to save a file nor use any other software.

&nbsp;

My one negative comment about the workflow is that it is not well suited for multiple people exchanging geometry together. For example, you cannot have one person generating Grasshopper data and another person receiving that data in Revit. The transfer HAS to be on the same machine and happen immediately. You cannot update the Grasshopper data and come in tomorrow to load in the new work done. My second negative comment, I lied, is that you cannot update the location of an Adaptive Component, but rather delete it and replace it. If you had any tags or other instance parameters added to the element, it would be lost.

&nbsp;

&nbsp;
<h3>Chameleon - GH:</h3>
On the Grasshopper side, it contains tools for transferring geometry both to and from Revit. Tools for transferring geometry to Revit are currently limited to Adaptive Components. In the Grasshopper plugin, there are currently four sections. Interoperability that deals with transferring between Revit, Simulation that deals with Sightlines, Utilities that deal with surface operations, and View that deals with camera positioning.
<p style="text-align: justify;"><img class="size-full wp-image-280" style="border: 0px; margin: 0px;" alt="Chameleon_GH_Revit Tools" src="/images/2013/04/Chameleon_GH_Revit-Tools.jpg" width="226" height="199" /> <img class="alignnone size-full wp-image-281" style="margin: 0px; border: 0px;" alt="Chameleon_GH_Simulation Tools" src="/images/2013/04/Chameleon_GH_Simulation-Tools.jpg" width="139" height="100" /> <img class="alignnone size-full wp-image-282" style="border: 0px; margin: 0px;" alt="Chameleon_GH_Utility Tools" src="/images/2013/04/Chameleon_GH_Utility-Tools.jpg" width="165" height="147" /> <img class="alignnone size-full wp-image-283" style="border: 0px; margin: 0px;" alt="Chameleon_GH_View Tools" src="/images/2013/04/Chameleon_GH_View-Tools.jpg" width="168" height="172" /></p>
&nbsp;

&nbsp;
<h3>Chameleon - RVT</h3>
On the Revit addin, there are two sections. Three tools that deal with transfer to Grasshopper, and two tools for Curtain Grid operations. We will dive further into the Grasshopper to Revit workflow tools, but in no way is this to put more focus on those tools. The Curtain Grid tools are actually very powerful and allow you to create useful grid divisions that honestly should be built into Revit in the first place.

<img class="size-full wp-image-285 aligncenter" alt="Chameleon_Revit Tools" src="/images/2013/04/Chameleon_Revit-Tools.jpg" width="440" height="385" />

.
<h3>Grasshopper to Revit Workflow: Placing Adaptive Components</h3>
Beginning with a straightforward [button link="/images/2013/04/Chameleon.gh" color="#AAAAAA" size="1" style="1" dark="0" radius="auto" target="self"]Grasshopper Definition[/button] the End Points of some structure curves are streamed into Chameleon's Adaptive Component component. The Parameters input requires the Adaptive Component family inside of Revit to have a "Number" Instance Parameter, which is left out for this first go.

&nbsp;

<img class="size-full wp-image-320 aligncenter" alt="Chameleon_GH Def" src="/images/2013/04/Chameleon_GH-Def.jpg" width="1532" height="543" />

<img class="size-full wp-image-314 aligncenter" style="text-align: justify;" alt="Chameleon_GH_Revit Tools_AdaptComp" src="/images/2013/04/Chameleon_GH_Revit-Tools_AdaptComp.jpg" width="323" height="254" />

&nbsp;

&nbsp;

Once the Component is set to Activate, a window pops up telling you to activate the Adaptive Component in Revit.

&nbsp;

<img class="size-full wp-image-279 aligncenter" alt="Chameleon_GH Window" src="/images/2013/04/Chameleon_GH-Window.jpg" width="516" height="238" />

&nbsp;

&nbsp;

&nbsp;

Once clicked, a window pops up allowing you to select from all the Adaptive Components you have loaded in the project. I used this 4 point  [button link="/images/2013/04/4_Pt_Plane_01.rfa" color="#AAAAAA" size="1" style="1" dark="0" radius="auto" target="self"]Adaptive Component (rvt 2013)[/button] in the images below.

&nbsp;

<img class="size-full wp-image-287 aligncenter" alt="Chameleon_Revit Window" src="/images/2013/04/Chameleon_Revit-Window.jpg" width="860" height="710" />

&nbsp;

&nbsp;

Once selected, the add-in establishes a link with the Grasshopper components, transfers a gbxml file, parses the gbxml file very quickly, and places the adaptive component using the points we streamed into the Grasshopper component.

<strong>NOTE: What ever units you have set inside of Grasshopper, is the scale the components are placed inside the project. </strong>

<img class="size-full wp-image-286 aligncenter" alt="Chameleon_Revit Window Wait" src="/images/2013/04/Chameleon_Revit-Window-Wait.jpg" width="510" height="330" />

&nbsp;

<img class="size-full wp-image-291 aligncenter" alt="Chameleon_Revit_Adpt_Placed2" src="/images/2013/04/Chameleon_Revit_Adpt_Placed2.jpg" width="764" height="713" />
<img class="size-full wp-image-332 aligncenter" alt="Chameleon_Revit_Adpt_Placed" src="/images/2013/04/Chameleon_Revit_Adpt_Placed1.jpg" width="924" height="740" />

&nbsp;

&nbsp;
<h3></h3>
&nbsp;

&nbsp;

&nbsp;
