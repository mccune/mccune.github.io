---
layout: post
title: Grasshopper & Revit Interoperability - Adaptive Components via Geometry Gym
date: 2013-04-28 09:15
author: michael
comments: true
categories: [Geometry Gym, Grasshopper, IFC, Interoperability, Revit]
---
<img class="size-full wp-image-423 aligncenter" alt="GeometryGym" src="/images/2013/04/GeometryGym.jpg" width="125" height="125" />
<h3>About Geometry Gym:</h3>
The next plugin in the list of interop tools for Revit is one created by Geometry Gym. Geometry Gym is usually referred to as the plugin name, but it is technically a company created by the developer <a href="http://au.linkedin.com/pub/jon-mirtschin/8/4b5/a51">Jon Mirtschin</a>. The plugins that Jon has been developing has recently been gaining names, in particular is the powerhouse geometry tool set which is now called BullAnt. Formally called StructDrawRhino, BullAnt has a lot of useful tools that are not available anywhere else. Some great examples of what you can generate with this base tool set can be seen <a href="http://geometrygym.wikidot.com/summary">here</a>.
<p style="text-align: center;"><img class=" wp-image-424 aligncenter" alt="Geometry Gym - Grasshopper Panel" src="/images/2013/04/Geometry-Gym-Grasshopper-Panel.jpg" width="628" height="759" /></p>
&nbsp;
<h3>[divider top="1"]</h3>
<h3>Geometry Gym: BIM Tools</h3>
In addition to the BullAnt plugin, Jon has been actively developing a set of very powerful interop tools from Rhino/Grasshopper to Revit, Vasari, Tekla, SDNF, Oasys GSA, Robot, SAP 2000, SOFiSTiK, SPACEGASS, STRAND7. I recognize only a few of those! So obviously we are only going to talk about the Grasshopper to Revit tools for this post. You can download all of the interop tools on his blog <a href="http://geometrygym.wikidot.com/downloads">here</a>.

&nbsp;

Geometry Gym uses IFC, Industry Foundation Class, as the exchange format between Grasshopper and Revit. Because of this, the plugin comes packed with components for creating a proper IFC file with the proper relationships of IFC elements. Don't let the sheer number of components overwhelm you. Prepare yourself when you expand a tab and realize their are dozens of components that are hidden from the panel window! Jon realizes the intimidation this causes, but I promise that once you start to understand the structure of IFC, and more importantly how Jon has organized the panels, they become a lot more friendly.

<img class="alignnone size-large wp-image-450" alt="Geometry Gym - Grasshopper Home Panel" src="/images/2013/04/Geometry-Gym-Grasshopper-Home-Panel-840x39.jpg" width="840" height="39" />

&nbsp;

As with the other GH to RVT interop tools, I am going to briefly cover the available tabs of components that come with the plugin, but I will keep it brief for the purpose of keeping your attention. Another post on the Geometry Tools is way overdue.  From left to right on the GeoGym BIM tab.

&nbsp;

<strong>ggIFC Tab</strong>

The ggIFC components tab is where the basic IFC components live. Creating the entry points for the IFC file using the Building, Project, and Site components as well as defining Building Stories (Levels), Spaces, Materials, and Profiles are all often used components when building the IFC file.

<img class="alignnone size-full wp-image-445" alt="Geometry Gym - ggIFC_" src="/images/2013/04/Geometry-Gym-ggIFC_.jpg" width="168" height="72" />

<img class="alignnone size-full wp-image-444" alt="Geometry Gym - ggIFC" src="/images/2013/04/Geometry-Gym-ggIFC.jpg" width="600" height="483" />

&nbsp;

<strong>ggIFC Attributes Tab</strong>

The ggIFC Attributes components tab include components for creating Property Sets and values of specific types. These ultimately are streamed into element type components.

<img class="alignnone size-full wp-image-431" alt="Geometry Gym - ggIFC Attributes_" src="/images/2013/04/Geometry-Gym-ggIFC-Attributes_.jpg" width="139" height="74" />

<img class="alignnone size-full wp-image-430" alt="Geometry Gym - ggIFC Attributes" src="/images/2013/04/Geometry-Gym-ggIFC-Attributes.jpg" width="212" height="441" />

&nbsp;

<strong>ggIFC Elements Tab</strong>

The ggIFC Elements components tab, I think, is a tab full of misfit components. Jon may have to weigh in on the use of this tab. My version of Geometry Gym is also an unofficial release, so the tab layout may be in limbo.

<img class="alignnone size-full wp-image-437" alt="Geometry Gym - ggIFC Elements_" src="/images/2013/04/Geometry-Gym-ggIFC-Elements_.jpg" width="138" height="74" />

<img class="alignnone size-full wp-image-436" alt="Geometry Gym - ggIFC Elements" src="/images/2013/04/Geometry-Gym-ggIFC-Elements.jpg" width="189" height="195" />

&nbsp;

<strong>ggIFC Elements Building Tab</strong>

The ggIFC Elements Building components tab is where most of the magic happens. This is where you can create various Architectural IFC elements. You will notice that there are some duplicate components, but these are actually special case components. The components that end with "Standard Case" are used for creating Revit specific elements. This allows Jon to recreate native Revit elements even down to creating the Wall and Floor structural and material layers. The components that end in "Type" are for defining what type of element, and then the "Common Properties" components are for defining the properties most commonly associated with that element. So the sequence of the components generally go from "Common Properties" to "Type" to "IFC Element".

<img class="alignnone size-full wp-image-433" alt="Geometry Gym - ggIFC Elements Building_" src="/images/2013/04/Geometry-Gym-ggIFC-Elements-Building_.jpg" width="184" height="76" />

<img class="alignnone size-full wp-image-432" alt="Geometry Gym - ggIFC Elements Building" src="/images/2013/04/Geometry-Gym-ggIFC-Elements-Building.jpg" width="669" height="759" />

&nbsp;

<strong>ggIFC Element Services Tab</strong>

The ggIFC Element Services components tab is just like its Architectural counterpart, but Services related. There is no need to reiterate its usage.

<img class="alignnone size-full wp-image-435" alt="Geometry Gym - ggIFC Elements Services_" src="/images/2013/04/Geometry-Gym-ggIFC-Elements-Services_.jpg" width="194" height="74" />

<img class="alignnone size-full wp-image-434" alt="Geometry Gym - ggIFC Elements Services" src="/images/2013/04/Geometry-Gym-ggIFC-Elements-Services.jpg" width="517" height="411" />

&nbsp;

<strong>ggIFC Entity Tab</strong>

The ggIFC Entity components tab include components for bringing an IFC file into Grasshopper and decomposing it to gain access to the elements inside it. The Beam, Column, and Slab components are basically filter components that allow you to stream the product or representation through it and only return a Column.

<img class="alignnone size-full wp-image-439" alt="Geometry Gym - ggIFC Entity_" src="/images/2013/04/Geometry-Gym-ggIFC-Entity_.jpg" width="184" height="74" />

<img class="alignnone size-full wp-image-438" alt="Geometry Gym - ggIFC Entity" src="/images/2013/04/Geometry-Gym-ggIFC-Entity.jpg" width="270" height="405" />

&nbsp;

<strong>ggIFC Representations Tab</strong>

The ggIFC Representations components tab includes components for creating Line Styles, generic IFC geometry types like Curves, Verticies, Surfaces, and Solids. For efficiency, it is better to use the geometry type that best represents your representation. You may also notice some very interesting components like PointOnCurve.

<img class="alignnone size-full wp-image-441" alt="Geometry Gym - ggIFC Representations_" src="/images/2013/04/Geometry-Gym-ggIFC-Representations_.jpg" width="166" height="76" />

<img class="alignnone size-full wp-image-440" alt="Geometry Gym - ggIFC Representations" src="/images/2013/04/Geometry-Gym-ggIFC-Representations.jpg" width="487" height="504" />

&nbsp;

&nbsp;
<h3>[divider top="1"]</h3>
<h3>Grasshopper to Revit Workflow: Placing Adaptive Components</h3>
<strong>IFC Entry Points</strong>

Using the same base [button link="/images/2013/04/Geometry%20Gym.gh" color="#AAAAAA" size="1" style="1" dark="0" radius="auto" target="self"]Grasshopper Definition[/button] again, we will use only the components necessary for getting the Adaptive Component into Revit. This means that we need to build a very basic IFC file. To do that, we need to create the entry point by placing two components, IFC Building and IFC Project. These components come loaded with default values to streamline the process, so be sure to change them to make sense for your project. Every IFC file you build with Geometry Gym will need these two components.

<img class="size-full wp-image-461 aligncenter" alt="Geometry Gym - Project and Building" src="/images/2013/04/Geometry-Gym-Project-and-Building.jpg" width="305" height="256" />

&nbsp;

<strong>IFC Adaptive Component</strong>

Next we need to build up the IFC Element of an Adaptive Component. The Adaptive Component component for Geometry Gym is labeled "ggIFC Curtain Wall Standard Case Adaptive Component". I am not sure why it is that long, but it may have to do with helping you know which component to use to define its Type.  The three required inputs that are required is the Container (IFC Building), the Curtain Wall Type, and the Points for the Adaptive Points. We have two of those, so now we just need to define the Curtain Wall Type.

&nbsp;

One of the biggest advantages to using Geometry Gym to place Adaptive Components is that Geometry Gym can create the Adaptive Component for you! Though you do not have all the functionality as you do in Revit's Conceptual Modeling Environment, you can create some parametric relationships that are available in the IFC definitions. One of those relationships that has been implemented is the PointOnCurve component. After talking with Jon, defining a PointOnSurface is also available but not implemented yet. I think that would be a great addition.

&nbsp;

<strong>IFC Curtain Wall Type</strong>

Anyways, in the current release of Geometry Gym, we need to define "something" for the adaptive component whether it is in the Revit project already or not. This leads us to the required inputs of the Curtain Wall Type component. The only required input is the Representation input, though we really want to define a name as well. If the Name matches the name of an adaptive component in Revit, it will use that famiy. If the name does not exist, it will create what ever you have defined as the Representation as an adaptive component.

<img class="size-full wp-image-462 aligncenter" alt="Geometry Gym - Curtain Wall Type" src="/images/2013/04/Geometry-Gym-Curtain-Wall-Type.jpg" width="526" height="223" />

&nbsp;

<strong>IFC Representation</strong>

To create a representation for the adaptive component, we need to build up the component using IFC geometry types. The adaptive component that we have been using with the previous plugins is extremely straightforward to create in Geometry Gym. Starting with 4 points, we need to convert those into IFC Vertex Points. The order that we stream them together will define the placement order in Revit. The IFC Vertex Points are then used to create an IFC Face. The IFC Face is then streamed into a IFC Face Set component. In order to input into the Curtain Wall Type component we need to have a Representation Map, so we can just stream the Face or Face Set into the IFC Representation Map. The Representation Map component basically acts as a "block" that contains all kinds of geometry for IFC.

<img class="size-full wp-image-464 aligncenter" alt="Geometry Gym - Representation" src="/images/2013/04/Geometry-Gym-Representation.jpg" width="534" height="467" />

&nbsp;

&nbsp;

<strong>Final Defintion</strong>

The final definition ends up being a total of 15 components to create the Adaptive Component. Three of them though are standard and are used every time whether you are creating an entire building or just adaptive components. You will notice that the output of the Geometry Gym components is the IFC data itself. When you add or delete elements/component from the definition, the IFC data is recomputed and compressed. Even the numbers that are associating the elements and attributes are recomputed to make sure that there are no unused numbers.

<img class="alignnone size-large wp-image-429" alt="Geometry Gym - Create Adaptive Component" src="/images/2013/04/Geometry-Gym-Create-Adaptive-Component-840x405.jpg" width="840" height="405" />

&nbsp;

<strong>Bake IFC</strong>

When you are ready to save the [button link="/images/2013/04/GeometryGym.ifc" color="#AAAAAA" size="1" style="1" dark="0" radius="auto" target="self"]IFC File[/button], you can use the ggIFC BakeToFile component. This basically gathers all the IFC outputs of the Geometry Gym components and saves it to a folder location. The BakeToFile component also comes with some options that you should be aware of like the (IFC4 checkbox.

<img class="wp-image-467 aligncenter" alt="Geometry Gym - IFC Bake" src="/images/2013/04/Geometry-Gym-IFC-Bake.jpg" width="281" height="461" />

&nbsp;

<strong>Geometry Gym Revit Addin</strong>

To bring in an IFC into Revit, you need to use the addin developed by Geometry Gym. Revit can import in an IFC file, but it will not create native Revit elements. Even if you export an IFC from Revit and bring it back in it does not retain its intelligence. Jon is also using a few "tags" in the IFC that allow him to do cool stuff like create Materials, Layers, and Adaptive Components. When start the addin, a window will appear giving you some options. None of these apply to our example.

<img class="size-large wp-image-471 aligncenter" alt="Geometry Gym - Revit" src="/images/2013/04/Geometry-Gym-Revit.jpg" width="121" height="102" />

<img class="size-full wp-image-470 aligncenter" style="font-size: 13px;" alt="Geometry Gym - Revit 2" src="/images/2013/04/Geometry-Gym-Revit-2.jpg" width="670" height="373" />

&nbsp;

A few issues you may or may not run into during this process are the unit conversion and the compiling of the IFC in Grasshopper. The units need to make sense especially when using the Adaptive Component. In this example, I had to change the units in Rhino from Millimeters to Centermeters or larger. It would throw an error in Revit otherwise. The other issue pointed out by Jon is only temporary and will be fixed when the new Grasshopper version is released soon. I don't quite understand the problem, so I am not going to try to pretend that I do, but if you run into an issue with Revit throwing an error and you know it is not your units, try saving your Grasshopper definition, closing the definition (not GH), then reopening it. :)

&nbsp;
<h3>[divider top="1"]</h3>
&nbsp;

<strong>Comments</strong>

My comments for this workflow and plugin in general are mixed. Jon has put in an extreme amount of effort creating this plugin and actually developing a viable IFC importer and exporter for both Rhino and Revit (among other applications). If you have not dealt with him, you will be pleasantly impressed with his responsiveness and eagerness to help in any way. If you need a feature, he will add it in a heart beat. You can tell that he is passionate about it and that he is not trying to sell his services or product to you, but truly cares about your project. Unlike most of the GH tools, Jon actually provides support and training for his tools.

&nbsp;

Enough about the developer for now. As you will see, the tools and available properties that you can add to elements is mind boggling. There are some really interesting workflows and opportunities for non-Revit users that can come out of these tools. Learning the tools though is a pretty steep endeavor. The toughest part is learning how an IFC is constructed, but I actually think that using Geometry Gym is a really great way to get into IFC. It makes you understand the format at a fundamental level, much like Grasshopper makes you understand geometry at a fundamental level.

&nbsp;

In saying that, it takes an insane amount of components to create the simplest things because you have to build up everything that defines an element. There also seems to be some inflexibility with creating multiple IFC files in one definition. Currently all components are compiled into a single IFC file. It could be useful to separate the IFC Walls, IFC Slabs, and other elements from each other without having to disable the components. That way, if the Floors were updated but the Walls or Stairs were not, the team does not have to disable anything or import elements that did not change.

&nbsp;

I also think that through some creative customization of the GH component kernel, the amount of components could be reduced significantly.

&nbsp;

<strong>Other blog posts on Geometry Gym</strong>

For additional information, check out the <a href="http://bim42.com/tag/geometry-gym/">BIM 42 blog</a> and its Geometry Gym posts.

<img class="size-full wp-image-468 aligncenter" alt="Geometry Gym - Placed 1" src="/images/2013/04/Geometry-Gym-Placed-1.jpg" width="698" height="607" />
