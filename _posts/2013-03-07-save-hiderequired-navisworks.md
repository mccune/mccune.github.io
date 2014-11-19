---
layout: post
title: Using the "Save Hide/Required Attributes" Viewpoints Setting in Navisworks
date: 2013-03-07 00:36
author: michael
comments: true
categories: [Analysis, Coordination, Navisworks, Tips &amp; Tricks]
---
&nbsp;

When trying to set up a viewpoint inside of Navisworks, you often want to Hide other elements, systems, and trades that are around the specific clash you are calling out.  In hopes to help speed this process up, I tested out the "Save Hide/Required Attributes" setting for viewpoints.  This setting is in the Global Options window under Viewpoints.  This seems like a great thing, but without understanding its limitations, you can really waste a lot of time by having to redo a lot of previously saved Viewpoints.

&nbsp;

<img class="size-full wp-image-244 aligncenter" title="Viewpoints Settings" alt="Save Hide / Required Attributes" src="/images/2013/03/Viewpoint-Settings.jpg" width="664" height="637" />

&nbsp;

As you know there are several ways to "Select" elements in Navisworks in order to "Hide" them:

[list style="idea"]
<ul>
	<li>By Element</li>
	<li>By Property (Category, Level, Etc)</li>
	<li>By Selection Set</li>
	<li>By Search Set</li>
	<li>By File (NWD,NWC,Non-native)</li>
</ul>
[/list]

Am I missing any? If you also consider that there are two ways to hide, "Hide Selected" and "Hide Unselected". That means that there are actually 14 ways to Hide elements not including combinations of selection methods.

&nbsp;

Now with the "Save Hide/Required Attributes" box checked in the Viewpoints settings, you would figure by the title of the setting that it would save what you have Hidden/Shown no matter HOW you hide elements.  Not so.... As noted in this <a href="http://forums.autodesk.com/t5/Autodesk-Navisworks/losing-saved-viewpoints-hidden-attributes/td-p/3571594">unanswered forum post</a> on one of Autodesk's Discussion groups from late last year, this can lead to some serious frustration and rework to fix the viewpoints when it is finally realized further into the project.

&nbsp;
<p style="text-align: center;"><a href="/images/2013/03/Unanswered-Forum-Post.jpg"><img class="size-full wp-image-245 aligncenter" title="Unanswered Forum Post" alt="Unanswered Forum Post" src="/images/2013/03/Unanswered-Forum-Post.jpg" width="959" height="879" /></a></p>
&nbsp;

If you really think about it, the reason this happens makes quite a lot of sense.  When you hide an element, Navisworks remembers that elements GUID.  If a model is updated and that GUID remains in the model, it stays hidden. If there are new GUID's that are created, which is guaranteed to happen as models progress and elements are added, Navisworks has no saved Hidden Attribute of those new GUID's.  This ends up causing your viewpoint to look like a hot mess, potentially obstructing your view of the object you are calling attention to.

So do any of the Hide methods work?  Is there any way that we can keep those new added elements from appearing in our scene?  It would make a lot of sense that when selecting By Property, By Search Set, or By File new elements would stay hidden since it seems like they all work like a Search Set.  By that I mean, look through the model, if it contains this property or is in this Search Set or is in this file then Hide it!   However, this is not how it works unfortunately.   Hopefully this could be addressed in a future release of Navisworks, but for now I would steer clear of using the Save Hide Attribute in this way.

&nbsp;

There is some hope for this setting though.  The only selection method found to work that actually keeps new unwanted elements Hidden and wanted elements Shown is the 'By File" method.  However, there are still inconsistencies with this method!  It only works if you select an NWD.  For some reason, when selecting NWC's and other Non-native file formats like IFC and DWG, the setting does not work as expected. If additional files/models are added underneath the NWD's they will be hidden as they are a child of the NWD.  So even though it does not work for all formats, you can wrap the disciplines up into NWDs like so...

&nbsp;
<p style="text-align: center;"><a href="/images/2013/03/Selection-Tree.jpg"><img class="aligncenter size-full wp-image-253" title="Selection Tree" alt="Selection Tree" src="/images/2013/03/Selection-Tree.jpg" width="178" height="174" /></a></p>
The instance where this does not work again deals with the parent child relationship of the file linking strategy.  In the example selection tree above, if I were to select the Arch, MEP, and Struct NWD's without selecting the DESIGN.nwd that they are contained within and Hide them, then any new file I add later within the DESIGN.nwd would not be hidden.  On the contrary, if I would have selected the DESIGN.nwd and not any of the NWD's within it and Hidden it, then any new file I add later WOULD be hidden. This is essentially why NWC's and other formats do not work as standalone files.  Try to wrap them up inside an NWD.

&nbsp;

There are also some added benefits to using this setting when you are wanting to capture the Clash Detective Display Style of "Dim Other."  As noted in this <a href="http://www.augi.com/library/exploring-options-in-navisworks">blog post on AUGI</a>,  when this setting is enabled, your viewpoint will ghost all other elements that are not clashing.

&nbsp;

If you still want to use this setting in your workflow, I recommend you preset some Viewpoints that can get you back to a saved state of the model.  Having these viewpoints will allow you to "reset" the colors of the elements to your color scheme, if you are coloring elements by trade, system, etc.  Having saved viewpoints of entire or select trades hidden is also extremely helpful when documenting new clashes between trades.  For example when documenting an issue between Mechanical and Structure, you can click on your saved Viewpoint to just show Mechanical and Structure, then click back on your issue in the Clash Detective results tab, and you then already have the colors reset and the appropriate trades visible.

&nbsp;

I am curious to know if anyone is actually using this setting and how if not described above.
