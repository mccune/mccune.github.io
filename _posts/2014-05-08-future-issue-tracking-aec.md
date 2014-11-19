---
layout: post
title: The Future of Issue Tracking for the AEC. Will it be AEC software?
date: 2014-05-08 20:44
author: michael
comments: true
categories: [Analysis, Autodesk, Coordination, Excel, Issue Tracking, Jira, Navisworks, none, SMC, Solibri]
---
<img class="aligncenter wp-image-1328 size-full" src="http://collectivebim.com/wp-content/uploads/2014/05/Issue-Tracking-e1399595905871.png" alt="Issue Tracking" width="779" height="334" />

More often than not, projects are now requiring that the design and construction models undergo a clash detection analysis. At the moment this process is manually performed after the modeling has occured. Hopefully modeling software will soon just include clash detection logic, so as we are modeling it can tell us “Hey, there is a giant beam here! Don’t place that duct here will you?” Until then we have to use specialised analysis software to help us find those areas where we did not coordinate properly with our consultants.

&nbsp;

<b><i>Discovering clashes</i></b> in design and construction models is a relatively common capability of software used by the AEC industry. However, once a clash is found, there are only a few options for reporting and monitoring the clash’s lifecycle. In most software, the developers expect you to manage the recurring clashes and attached meta-data solely within the software – packed away in a module that is inaccessible to any non-savvy unsubscribed software user. In some software you are forced to share clashes and attached meta-data via a single file (Excel, BCF, HTML) in order to share with users using different tools. These are not acceptable implementations for real situations.

&nbsp;
<h1>Why issue tracking in the first place?</h1>
Issue Tracking, or bug tracking, is a quality assurance process commonly used by software developers and support centers. At CASE, we make no distinction between tracking “bugs” in our software and tracking “coordination issues” in buildings we are involved with. We regularly set out the BIM strategy and provide BIM Management on projects where issue tracking plays an enormous role for monitoring the implementation of a project’s BIM process. Issue tracking is essentially the main component of the Monitoring and Controlling phase, the phase that runs concurrently with the Execution phase of the project.

&nbsp;

Issue tracking as a process is not new to the building industry. It happens on most construction projects and can result in formal communications sent as Requests For Information (RFIs) that are usually directed at the design team for input and resolution. Instead of waiting to find issues on site, we now use analysis software to find issues like geometric conflicts much earlier in the design and construction process. As a result, the issue tracking process, and the value it brings, has been pushed further upstream into the design process.

&nbsp;

When a model is analyzed during the design phase, a clash detection analysis might identify tens of thousands of clashes. A clash is a singular instance where two geometries are occupying the same space or do not maintain a required distance. At CASE, we make a clear distinction between what is a clash and what is an issue. A clash lets us know that our requirements are not met. An issue is an action item distributed to the team that defines the underlying reason why there is a clash. An issue can be a single clash, but is more often than not a group of clashes.

&nbsp;

So what value does issue tracking actually bring? Well, when issues are found, they need to be communicated to the team. The information about the issue, or meta-data, becomes extremely important to also track in order for others to understand the issue. Information like where is the issue located in the building? Who is involved in the issue? Who should take ownership to resolve this issue? How critical is this issue at this point in time? Is this a new issue or an existing issue? How long has this issue been unresolved? The value that issue tracking brings is the ability to capture, share, and monitor the data vital to resolving the issues.

&nbsp;

Once the issues are identified and delivered to the team, the parties involved will discuss how to resolve the issues. Often this discussion occurs through emails, RFIs, and in person meetings. Ideally these discussions should be captured and associated with the issues so that there is an accessible and transparent history to how an issue is being resolved.

&nbsp;

In addition to the value that issue tracking brings during coordination, it also offers the opportunity to identify larger overall management trends. With a database of issues at hand, it is possible to see which design decisions caused the most conflicts, which issues were the most time consuming, and which problems caused a delay in the project schedule. When done properly, issue tracking is not only about improving buildings, it is also about improving design processes. At CASE we have developed a process for tracking issues that automatically provides us with this level of feedback. This provides CASE with an amazing understanding of all the projects, and more importantly the process, allowing us to continually advance the way we deliver projects.

&nbsp;
<h1>Traditional ways for issue tracking in the AEC</h1>
There are three common methods we have seen used for tracking issues in the building industry. The first – and the worst – is reporting via email. There is no need to go into why this is a bad idea. It should be clear from the fact that you often manage 300-3000 issues on a medium size project. How many emails does that equal? Often email is used to send reports generated by the analysis software. The report formats vary from HTML to PDF to Excel reports. The downside of these file based reports is that they are not bidirectional. They are simply snapshots of the issues at a moment in time. You cannot comment on them, change the status, or assign an issue to a user and feed that new information back into the system. Email is a dead end.

&nbsp;

The second method is to maintain a running list of issues inside a spreadsheet. This is a very common method and if set up properly it can be a fairly efficient way to manage a small number of issues. However, managing thousands or even hundreds of issues over the life of a project using a spreadsheet can quickly turn into a full time job. With field formats, macros, and charting, you can configure an informative and flexible system for issue tracking. It is however still a manual data entry task and a manual coordination process that is time consuming and subject to user-input errors.

&nbsp;

With both of these methods – email and spreadsheet – you are separated from the model environment and forced to work with images and text. Sure you could exchange the entire model file or add a url to the issue that directs the user to a cloud hosted model on Autodesk 360 Glue, but this would have to be done manually.

&nbsp;

The third method is to use coordination analysis software. The software vendors expect you to manage all the issues solely inside their analysis software. I truly wish this was actually possible. The workflow prescribed to us does not work in a real world scenario. The features favor finding clashes over managing them. With the few capabilities the software does have for managing issues, it keeps hidden from the rest of the team. To get a bit technical, in tools like Autodesk Navisworks and Autodesk 360 Glue, access to the results/issues are hidden from anyone who does not have the paid/full version of the software. In order for the issues to be seen in free viewers, the issues have to be added as viewpoints/slides or reported as HTML or PDF. This means we have to manage the issues in multiple places. Solibri Model Checker rises above the rest when it comes to seeing the analysis results. All results of a check can be seen in the free Solibri Model Viewer. However, every coordination analysis software on the market, including Solibri Model Checker, Autodesk Navisworks, and Autodesk 360 Glue, fall short in integrating the ability to properly track and manage issues in a real world environment.

&nbsp;

At a minimum, a proper issue tracking method should include the ability to:
<ul>
	<li>define the type of issue (clash, data deficiency, model craft)</li>
	<li>store meta-data about an issue (priority, location, date found)</li>
	<li>take an issue through a defined workflow / change of status</li>
	<li>manage comments from multiple parties</li>
	<li>define who is responsible for resolving the issue</li>
	<li>keep all information above intact throughout model development</li>
	<li>be accessed by entire team regardless of their platform or experience.</li>
</ul>
&nbsp;
<h1>AEC Software get us half way there.</h1>
Each AEC software handles the results of a model check differently. None of them, in my opinion, handle them very well. Most programs give you a tremendous amount of freedom in organizing data to analyze. On the other hand, none give you the capability to organize the results in a practical way. You may be saying, well Navisworks has a grouping functionality! The ability to group clashes is fantastic; however, retroactively grouping a giant dump of clashes is not efficient nor fun. It’s likes dumping a container full of LEGOs on the floor and being told you have to sort them by type and color. It gets us half way there. There has to be more intelligence built in.

&nbsp;

When Autodesk 360 Glue came out, it democratized clash detection by allowing anyone capable of uploading models to press four buttons and receive a ton of results. Although generating results is easier, understanding what the results mean is actually harder. It also lacks grouping functionality in its current state, but look on the bright side! You can email all 1000 clashes to your team directly from the software! It gets us half way there faster.

&nbsp;

Solibri Model Checker is a lot more intelligent in how it groups issues for you. Since Solibri knows which rule you are running and what results to expect, it does quite a bit of grunt work for you by grouping clashes by level, or by selection type, or by object type. This automatic grouping, however, is only customizable on 2% of its rulesets. Oddly enough, what is missing from Solibri Model Checker is the ability to group clashes into larger issues that behave like a singular issue. It again gets us half way there.

&nbsp;

Aside from those limitations of the most common AEC software, there is a larger problem with how every coordination analysis software on the market handles the life cycle of a clash. This one is a bit trickier and more difficult to solve. When issues are found with model elements, the issue lives and dies with the life of the model elements. If a duct element that was causing 50 clashes is deleted and redrawn, those 50 clashes will be marked as resolved and any meta-data associated with those clashes will go with it. If the new duct element doesn’t actually resolve the clashes, 50 brand new clashes will be created and will need to be grouped into an issue again. Why is this still a thing? Why can’t the software know that we just deleted the duct, redrew it, and that it is essentially the same issue? The clashes are roughly in the same location and involve the same element types. We need to move beyond clash detection based on geometry GUIDS and towards intelligent issue recognition that is only lightly connected to the geometry and free to live at a higher level.

&nbsp;

With all this criticism being thrown around – and at very specific software – I want to make it clear that we hope it is interpreted constructively. We want don’t want to bring the tools down, we want to help make them better. CASE uses most of the ones discussed in this article daily on live projects. We care deeply about them and we have been working to help our clients and the industry find the best way to use them. We are continuing to test and improve our processes. There is a better way.

&nbsp;

<a href="http://collectivebim.com/future-issue-tracking-bcf/">Next, let’s look into how the OpenBIM movement plans to solve this industry problem with BCF, BIM Collaboration Format!</a>
