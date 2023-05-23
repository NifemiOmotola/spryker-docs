---
title: App Composition Platform installation
description: Learn how to install the App Orchestration Platform.
template: concept-topic-template
redirect_from:
    - /docs/aop/user/intro-to-acp/acp-installation.html
---

This document describes how you can make your project ACP-ready and how you install ACP.

# Installing ACP in SCOS

{% info_block warningBox "" %}

To be eligible for ACP< your project must be hosted in the Spryker Cloud.

{% endinfo_block %}

The ACP catalog is embedded inside the Back Office and contains the list of applications you can connect to your shop.
You can access the ACP catalog only if you are a SCOS customer and have been enabled for ACP, which means that your SCOS environment is properly set up and registered with the ACP.

The process of installing ACP on SCOS is also called *ACP enablement*. It is a multi-step process, which requires steps to be taken by you and by Spryker. The first step implies making your SCOS project *ACP-ready*, meaning that the required ACP modules are up-to-date and the SCOS Cloud environment is configured correctly. The second step is making your project *ACP-enabled*, which implies registering your SCOS project with the Spryker's ACP, so that the ACP Catalog in the Back Office can interact with ACP. This enables you to browse, connect, configure all ACP applications for use with SCOS.

The following diagram outlines the different steps of the ACP enablement process and responsibilities for executing them.

<div class="mxgraph" style="max-width:100%;border:1px solid transparent;" data-mxgraph="{&quot;highlight&quot;:&quot;#0000ff&quot;,&quot;nav&quot;:true,&quot;resize&quot;:true,&quot;toolbar&quot;:&quot;zoom layers tags lightbox&quot;,&quot;edit&quot;:&quot;_blank&quot;,&quot;xml&quot;:&quot;&lt;mxfile host=\&quot;app.diagrams.net\&quot; modified=\&quot;2023-05-23T13:25:26.801Z\&quot; agent=\&quot;Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/113.0.0.0 Safari/537.36\&quot; etag=\&quot;Ejuq2whL4FPb4OVSH-Me\&quot; version=\&quot;21.3.2\&quot;&gt;\n  &lt;diagram name=\&quot;Страница 1\&quot; id=\&quot;0AxMdV5PH_cISPjeI29k\&quot;&gt;\n    &lt;mxGraphModel dx=\&quot;2474\&quot; dy=\&quot;1116\&quot; grid=\&quot;1\&quot; gridSize=\&quot;10\&quot; guides=\&quot;1\&quot; tooltips=\&quot;1\&quot; connect=\&quot;1\&quot; arrows=\&quot;1\&quot; fold=\&quot;1\&quot; page=\&quot;0\&quot; pageScale=\&quot;1\&quot; pageWidth=\&quot;827\&quot; pageHeight=\&quot;1169\&quot; math=\&quot;0\&quot; shadow=\&quot;0\&quot;&gt;\n      &lt;root&gt;\n        &lt;mxCell id=\&quot;0\&quot; /&gt;\n        &lt;mxCell id=\&quot;1\&quot; parent=\&quot;0\&quot; /&gt;\n        &lt;mxCell id=\&quot;AaxAhCZwYhS3f6JuZ0fs-32\&quot; value=\&quot;&amp;lt;b&amp;gt;&amp;lt;font color=&amp;quot;#ffffff&amp;quot;&amp;gt;Customer/SI&amp;lt;/font&amp;gt;&amp;lt;/b&amp;gt;\&quot; style=\&quot;whiteSpace=wrap;html=1;aspect=fixed;fillColor=#EB553c;strokeColor=#eb553c;\&quot; parent=\&quot;1\&quot; vertex=\&quot;1\&quot;&gt;\n          &lt;mxGeometry x=\&quot;-80\&quot; y=\&quot;132\&quot; width=\&quot;80\&quot; height=\&quot;80\&quot; as=\&quot;geometry\&quot; /&gt;\n        &lt;/mxCell&gt;\n        &lt;mxCell id=\&quot;AaxAhCZwYhS3f6JuZ0fs-33\&quot; value=\&quot;&amp;lt;b&amp;gt;&amp;lt;font color=&amp;quot;#ffffff&amp;quot;&amp;gt;Spryker (OPS/ACP)&amp;lt;/font&amp;gt;&amp;lt;/b&amp;gt;\&quot; style=\&quot;whiteSpace=wrap;html=1;aspect=fixed;fillColor=#1ebea0;strokeColor=#1EBEA0;\&quot; parent=\&quot;1\&quot; vertex=\&quot;1\&quot;&gt;\n          &lt;mxGeometry x=\&quot;-80\&quot; y=\&quot;252\&quot; width=\&quot;80\&quot; height=\&quot;80\&quot; as=\&quot;geometry\&quot; /&gt;\n        &lt;/mxCell&gt;\n        &lt;mxCell id=\&quot;AaxAhCZwYhS3f6JuZ0fs-34\&quot; value=\&quot;\&quot; style=\&quot;endArrow=none;dashed=1;html=1;rounded=0;\&quot; parent=\&quot;1\&quot; edge=\&quot;1\&quot;&gt;\n          &lt;mxGeometry width=\&quot;50\&quot; height=\&quot;50\&quot; relative=\&quot;1\&quot; as=\&quot;geometry\&quot;&gt;\n            &lt;mxPoint x=\&quot;41\&quot; y=\&quot;332\&quot; as=\&quot;sourcePoint\&quot; /&gt;\n            &lt;mxPoint x=\&quot;41\&quot; y=\&quot;132\&quot; as=\&quot;targetPoint\&quot; /&gt;\n          &lt;/mxGeometry&gt;\n        &lt;/mxCell&gt;\n        &lt;mxCell id=\&quot;AaxAhCZwYhS3f6JuZ0fs-50\&quot; style=\&quot;edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;\&quot; parent=\&quot;1\&quot; source=\&quot;AaxAhCZwYhS3f6JuZ0fs-35\&quot; target=\&quot;AaxAhCZwYhS3f6JuZ0fs-36\&quot; edge=\&quot;1\&quot;&gt;\n          &lt;mxGeometry relative=\&quot;1\&quot; as=\&quot;geometry\&quot; /&gt;\n        &lt;/mxCell&gt;\n        &lt;mxCell id=\&quot;AaxAhCZwYhS3f6JuZ0fs-35\&quot; value=\&quot;&amp;lt;font style=&amp;quot;font-size: 9px;&amp;quot; color=&amp;quot;#ffffff&amp;quot;&amp;gt;SCOS is updated to the latest module versions required for ACP and Apps&amp;lt;/font&amp;gt;\&quot; style=\&quot;whiteSpace=wrap;html=1;aspect=fixed;fillColor=#EB553c;strokeColor=#eb553c;\&quot; parent=\&quot;1\&quot; vertex=\&quot;1\&quot;&gt;\n          &lt;mxGeometry x=\&quot;80\&quot; y=\&quot;132\&quot; width=\&quot;88\&quot; height=\&quot;88\&quot; as=\&quot;geometry\&quot; /&gt;\n        &lt;/mxCell&gt;\n        &lt;mxCell id=\&quot;AaxAhCZwYhS3f6JuZ0fs-51\&quot; style=\&quot;edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;\&quot; parent=\&quot;1\&quot; source=\&quot;AaxAhCZwYhS3f6JuZ0fs-36\&quot; target=\&quot;AaxAhCZwYhS3f6JuZ0fs-37\&quot; edge=\&quot;1\&quot;&gt;\n          &lt;mxGeometry relative=\&quot;1\&quot; as=\&quot;geometry\&quot; /&gt;\n        &lt;/mxCell&gt;\n        &lt;mxCell id=\&quot;AaxAhCZwYhS3f6JuZ0fs-36\&quot; value=\&quot;&amp;lt;font style=&amp;quot;font-size: 9px;&amp;quot; color=&amp;quot;#ffffff&amp;quot;&amp;gt;SCOS is configured to activate ACP catalog in the Back Office&amp;lt;/font&amp;gt;\&quot; style=\&quot;whiteSpace=wrap;html=1;aspect=fixed;fillColor=#EB553c;strokeColor=#eb553c;\&quot; parent=\&quot;1\&quot; vertex=\&quot;1\&quot;&gt;\n          &lt;mxGeometry x=\&quot;190\&quot; y=\&quot;132\&quot; width=\&quot;88\&quot; height=\&quot;88\&quot; as=\&quot;geometry\&quot; /&gt;\n        &lt;/mxCell&gt;\n        &lt;mxCell id=\&quot;AaxAhCZwYhS3f6JuZ0fs-52\&quot; value=\&quot;\&quot; style=\&quot;edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;\&quot; parent=\&quot;1\&quot; source=\&quot;AaxAhCZwYhS3f6JuZ0fs-37\&quot; target=\&quot;AaxAhCZwYhS3f6JuZ0fs-38\&quot; edge=\&quot;1\&quot;&gt;\n          &lt;mxGeometry relative=\&quot;1\&quot; as=\&quot;geometry\&quot; /&gt;\n        &lt;/mxCell&gt;\n        &lt;mxCell id=\&quot;AaxAhCZwYhS3f6JuZ0fs-37\&quot; value=\&quot;&amp;lt;font style=&amp;quot;font-size: 9px;&amp;quot; color=&amp;quot;#ffffff&amp;quot;&amp;gt;SCOS environment variable keys are prepared&amp;lt;/font&amp;gt;\&quot; style=\&quot;whiteSpace=wrap;html=1;aspect=fixed;fillColor=#EB553c;strokeColor=#eb553c;\&quot; parent=\&quot;1\&quot; vertex=\&quot;1\&quot;&gt;\n          &lt;mxGeometry x=\&quot;300\&quot; y=\&quot;132\&quot; width=\&quot;88\&quot; height=\&quot;88\&quot; as=\&quot;geometry\&quot; /&gt;\n        &lt;/mxCell&gt;\n        &lt;mxCell id=\&quot;AaxAhCZwYhS3f6JuZ0fs-55\&quot; style=\&quot;edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;\&quot; parent=\&quot;1\&quot; source=\&quot;AaxAhCZwYhS3f6JuZ0fs-38\&quot; target=\&quot;AaxAhCZwYhS3f6JuZ0fs-40\&quot; edge=\&quot;1\&quot;&gt;\n          &lt;mxGeometry relative=\&quot;1\&quot; as=\&quot;geometry\&quot; /&gt;\n        &lt;/mxCell&gt;\n        &lt;mxCell id=\&quot;AaxAhCZwYhS3f6JuZ0fs-38\&quot; value=\&quot;&amp;lt;span style=&amp;quot;--tw-border-spacing-x: 0; --tw-border-spacing-y: 0; --tw-translate-x: 0; --tw-translate-y: 0; --tw-rotate: 0; --tw-skew-x: 0; --tw-skew-y: 0; --tw-scale-x: 1; --tw-scale-y: 1; --tw-pan-x: ; --tw-pan-y: ; --tw-pinch-zoom: ; --tw-scroll-snap-strictness: proximity; --tw-ordinal: ; --tw-slashed-zero: ; --tw-numeric-figure: ; --tw-numeric-spacing: ; --tw-numeric-fraction: ; --tw-ring-inset: ; --tw-ring-offset-width: 0px; --tw-ring-offset-color: #fff; --tw-ring-color: rgb(59 130 246 / 0.5); --tw-ring-offset-shadow: 0 0 #0000; --tw-ring-shadow: 0 0 #0000; --tw-shadow: 0 0 #0000; --tw-shadow-colored: 0 0 #0000; --tw-blur: ; --tw-brightness: ; --tw-contrast: ; --tw-grayscale: ; --tw-hue-rotate: ; --tw-invert: ; --tw-saturate: ; --tw-sepia: ; --tw-drop-shadow: ; --tw-backdrop-blur: ; --tw-backdrop-brightness: ; --tw-backdrop-contrast: ; --tw-backdrop-grayscale: ; --tw-backdrop-hue-rotate: ; --tw-backdrop-invert: ; --tw-backdrop-opacity: ; --tw-backdrop-saturate: ; --tw-backdrop-sepia: ; border-color: var(--border-color);&amp;quot;&amp;gt;&amp;lt;font style=&amp;quot;--tw-border-spacing-x: 0; --tw-border-spacing-y: 0; --tw-translate-x: 0; --tw-translate-y: 0; --tw-rotate: 0; --tw-skew-x: 0; --tw-skew-y: 0; --tw-scale-x: 1; --tw-scale-y: 1; --tw-pan-x: ; --tw-pan-y: ; --tw-pinch-zoom: ; --tw-scroll-snap-strictness: proximity; --tw-ordinal: ; --tw-slashed-zero: ; --tw-numeric-figure: ; --tw-numeric-spacing: ; --tw-numeric-fraction: ; --tw-ring-inset: ; --tw-ring-offset-width: 0px; --tw-ring-offset-color: #fff; --tw-ring-color: rgb(59 130 246 / 0.5); --tw-ring-offset-shadow: 0 0 #0000; --tw-ring-shadow: 0 0 #0000; --tw-shadow: 0 0 #0000; --tw-shadow-colored: 0 0 #0000; --tw-blur: ; --tw-brightness: ; --tw-contrast: ; --tw-grayscale: ; --tw-hue-rotate: ; --tw-invert: ; --tw-saturate: ; --tw-sepia: ; --tw-drop-shadow: ; --tw-backdrop-blur: ; --tw-backdrop-brightness: ; --tw-backdrop-contrast: ; --tw-backdrop-grayscale: ; --tw-backdrop-hue-rotate: ; --tw-backdrop-invert: ; --tw-backdrop-opacity: ; --tw-backdrop-saturate: ; --tw-backdrop-sepia: ; border-color: var(--border-color); font-size: 9px;&amp;quot; color=&amp;quot;#ffffff&amp;quot;&amp;gt;SCOS environment variable keys are configured&amp;lt;/font&amp;gt;&amp;lt;/span&amp;gt;\&quot; style=\&quot;whiteSpace=wrap;html=1;aspect=fixed;fillColor=#EB553c;strokeColor=#eb553c;\&quot; parent=\&quot;1\&quot; vertex=\&quot;1\&quot;&gt;\n          &lt;mxGeometry x=\&quot;410\&quot; y=\&quot;132\&quot; width=\&quot;88\&quot; height=\&quot;88\&quot; as=\&quot;geometry\&quot; /&gt;\n        &lt;/mxCell&gt;\n        &lt;mxCell id=\&quot;AaxAhCZwYhS3f6JuZ0fs-40\&quot; value=\&quot;&amp;lt;font style=&amp;quot;font-size: 9px;&amp;quot; color=&amp;quot;#ffffff&amp;quot;&amp;gt;SCOS is &amp;quot;&amp;lt;b&amp;gt;ACP-ready&amp;lt;/b&amp;gt;&amp;quot;&amp;lt;/font&amp;gt;\&quot; style=\&quot;rhombus;whiteSpace=wrap;html=1;fillColor=#EB553C;strokeColor=#EB553C;\&quot; parent=\&quot;1\&quot; vertex=\&quot;1\&quot;&gt;\n          &lt;mxGeometry x=\&quot;520\&quot; y=\&quot;132\&quot; width=\&quot;110\&quot; height=\&quot;98\&quot; as=\&quot;geometry\&quot; /&gt;\n        &lt;/mxCell&gt;\n        &lt;mxCell id=\&quot;AaxAhCZwYhS3f6JuZ0fs-56\&quot; style=\&quot;edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;\&quot; parent=\&quot;1\&quot; source=\&quot;AaxAhCZwYhS3f6JuZ0fs-43\&quot; target=\&quot;AaxAhCZwYhS3f6JuZ0fs-45\&quot; edge=\&quot;1\&quot;&gt;\n          &lt;mxGeometry relative=\&quot;1\&quot; as=\&quot;geometry\&quot; /&gt;\n        &lt;/mxCell&gt;\n        &lt;mxCell id=\&quot;AaxAhCZwYhS3f6JuZ0fs-43\&quot; value=\&quot;&amp;lt;font color=&amp;quot;#ffffff&amp;quot; style=&amp;quot;font-size: 9px;&amp;quot;&amp;gt;SCOS is &amp;quot;&amp;lt;/font&amp;gt;&amp;lt;b style=&amp;quot;--tw-border-spacing-x: 0; --tw-border-spacing-y: 0; --tw-translate-x: 0; --tw-translate-y: 0; --tw-rotate: 0; --tw-skew-x: 0; --tw-skew-y: 0; --tw-scale-x: 1; --tw-scale-y: 1; --tw-pan-x: ; --tw-pan-y: ; --tw-pinch-zoom: ; --tw-scroll-snap-strictness: proximity; --tw-ordinal: ; --tw-slashed-zero: ; --tw-numeric-figure: ; --tw-numeric-spacing: ; --tw-numeric-fraction: ; --tw-ring-inset: ; --tw-ring-offset-width: 0px; --tw-ring-offset-color: #fff; --tw-ring-color: rgb(59 130 246 / 0.5); --tw-ring-offset-shadow: 0 0 #0000; --tw-ring-shadow: 0 0 #0000; --tw-shadow: 0 0 #0000; --tw-shadow-colored: 0 0 #0000; --tw-blur: ; --tw-brightness: ; --tw-contrast: ; --tw-grayscale: ; --tw-hue-rotate: ; --tw-invert: ; --tw-saturate: ; --tw-sepia: ; --tw-drop-shadow: ; --tw-backdrop-blur: ; --tw-backdrop-brightness: ; --tw-backdrop-contrast: ; --tw-backdrop-grayscale: ; --tw-backdrop-hue-rotate: ; --tw-backdrop-invert: ; --tw-backdrop-opacity: ; --tw-backdrop-saturate: ; --tw-backdrop-sepia: ; border-color: var(--border-color); color: rgb(255, 255, 255); font-size: 9px;&amp;quot;&amp;gt;ACP-enabled&amp;lt;/b&amp;gt;&amp;lt;span style=&amp;quot;color: rgb(255, 255, 255); font-size: 9px;&amp;quot;&amp;gt;&amp;quot;&amp;lt;/span&amp;gt;\&quot; style=\&quot;rhombus;whiteSpace=wrap;html=1;fillColor=#EB553C;strokeColor=#EB553C;\&quot; parent=\&quot;1\&quot; vertex=\&quot;1\&quot;&gt;\n          &lt;mxGeometry x=\&quot;670\&quot; y=\&quot;132\&quot; width=\&quot;110\&quot; height=\&quot;98\&quot; as=\&quot;geometry\&quot; /&gt;\n        &lt;/mxCell&gt;\n        &lt;mxCell id=\&quot;AaxAhCZwYhS3f6JuZ0fs-45\&quot; value=\&quot;&amp;lt;font style=&amp;quot;font-size: 9px;&amp;quot; color=&amp;quot;#ffffff&amp;quot;&amp;gt;&amp;amp;nbsp;&amp;lt;b&amp;gt;ACP&amp;lt;br&amp;gt;&amp;amp;nbsp;catalog&amp;lt;/b&amp;gt; can be fully used with SCOS&amp;lt;/font&amp;gt;\&quot; style=\&quot;rhombus;whiteSpace=wrap;html=1;fillColor=#EB553C;strokeColor=#EB553C;\&quot; parent=\&quot;1\&quot; vertex=\&quot;1\&quot;&gt;\n          &lt;mxGeometry x=\&quot;810\&quot; y=\&quot;127\&quot; width=\&quot;110\&quot; height=\&quot;108\&quot; as=\&quot;geometry\&quot; /&gt;\n        &lt;/mxCell&gt;\n        &lt;mxCell id=\&quot;AaxAhCZwYhS3f6JuZ0fs-58\&quot; style=\&quot;edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=0.5;exitY=0;exitDx=0;exitDy=0;entryX=0.5;entryY=1;entryDx=0;entryDy=0;\&quot; parent=\&quot;1\&quot; source=\&quot;AaxAhCZwYhS3f6JuZ0fs-46\&quot; target=\&quot;AaxAhCZwYhS3f6JuZ0fs-37\&quot; edge=\&quot;1\&quot;&gt;\n          &lt;mxGeometry relative=\&quot;1\&quot; as=\&quot;geometry\&quot; /&gt;\n        &lt;/mxCell&gt;\n        &lt;mxCell id=\&quot;AaxAhCZwYhS3f6JuZ0fs-46\&quot; value=\&quot;&amp;lt;font style=&amp;quot;font-size: 9px;&amp;quot; color=&amp;quot;#ffffff&amp;quot;&amp;gt;Customer Cloud Infrastructure is updated with ACP components&amp;lt;/font&amp;gt;\&quot; style=\&quot;whiteSpace=wrap;html=1;aspect=fixed;fillColor=#1EBEA0;strokeColor=#1EBEA0;\&quot; parent=\&quot;1\&quot; vertex=\&quot;1\&quot;&gt;\n          &lt;mxGeometry x=\&quot;300\&quot; y=\&quot;252\&quot; width=\&quot;88\&quot; height=\&quot;88\&quot; as=\&quot;geometry\&quot; /&gt;\n        &lt;/mxCell&gt;\n        &lt;mxCell id=\&quot;AaxAhCZwYhS3f6JuZ0fs-61\&quot; value=\&quot;\&quot; style=\&quot;edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;\&quot; parent=\&quot;1\&quot; source=\&quot;AaxAhCZwYhS3f6JuZ0fs-47\&quot; target=\&quot;AaxAhCZwYhS3f6JuZ0fs-38\&quot; edge=\&quot;1\&quot;&gt;\n          &lt;mxGeometry relative=\&quot;1\&quot; as=\&quot;geometry\&quot; /&gt;\n        &lt;/mxCell&gt;\n        &lt;mxCell id=\&quot;AaxAhCZwYhS3f6JuZ0fs-47\&quot; value=\&quot;&amp;lt;font style=&amp;quot;font-size: 9px;&amp;quot; color=&amp;quot;#ffffff&amp;quot;&amp;gt;Values for Customer env variables are created based on Customer&amp;#39;s Cloud ACP components&amp;lt;/font&amp;gt;\&quot; style=\&quot;whiteSpace=wrap;html=1;aspect=fixed;fillColor=#1EBEA0;strokeColor=#1EBEA0;align=center;\&quot; parent=\&quot;1\&quot; vertex=\&quot;1\&quot;&gt;\n          &lt;mxGeometry x=\&quot;410\&quot; y=\&quot;252\&quot; width=\&quot;88\&quot; height=\&quot;88\&quot; as=\&quot;geometry\&quot; /&gt;\n        &lt;/mxCell&gt;\n        &lt;mxCell id=\&quot;AaxAhCZwYhS3f6JuZ0fs-60\&quot; style=\&quot;edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;exitX=1;exitY=0.5;exitDx=0;exitDy=0;entryX=0.5;entryY=1;entryDx=0;entryDy=0;\&quot; parent=\&quot;1\&quot; source=\&quot;AaxAhCZwYhS3f6JuZ0fs-48\&quot; target=\&quot;AaxAhCZwYhS3f6JuZ0fs-43\&quot; edge=\&quot;1\&quot;&gt;\n          &lt;mxGeometry relative=\&quot;1\&quot; as=\&quot;geometry\&quot; /&gt;\n        &lt;/mxCell&gt;\n        &lt;mxCell id=\&quot;AaxAhCZwYhS3f6JuZ0fs-48\&quot; value=\&quot;&amp;lt;font style=&amp;quot;font-size: 9px;&amp;quot; color=&amp;quot;#ffffff&amp;quot;&amp;gt;Register Customer SCOS with ACP&amp;lt;/font&amp;gt;\&quot; style=\&quot;whiteSpace=wrap;html=1;aspect=fixed;fillColor=#1EBEA0;strokeColor=#1EBEA0;\&quot; parent=\&quot;1\&quot; vertex=\&quot;1\&quot;&gt;\n          &lt;mxGeometry x=\&quot;600\&quot; y=\&quot;252\&quot; width=\&quot;88\&quot; height=\&quot;88\&quot; as=\&quot;geometry\&quot; /&gt;\n        &lt;/mxCell&gt;\n        &lt;mxCell id=\&quot;AaxAhCZwYhS3f6JuZ0fs-59\&quot; value=\&quot;\&quot; style=\&quot;endArrow=classic;html=1;rounded=0;exitX=0.5;exitY=1;exitDx=0;exitDy=0;entryX=0;entryY=0.5;entryDx=0;entryDy=0;\&quot; parent=\&quot;1\&quot; source=\&quot;AaxAhCZwYhS3f6JuZ0fs-40\&quot; target=\&quot;AaxAhCZwYhS3f6JuZ0fs-48\&quot; edge=\&quot;1\&quot;&gt;\n          &lt;mxGeometry width=\&quot;50\&quot; height=\&quot;50\&quot; relative=\&quot;1\&quot; as=\&quot;geometry\&quot;&gt;\n            &lt;mxPoint x=\&quot;540\&quot; y=\&quot;282\&quot; as=\&quot;sourcePoint\&quot; /&gt;\n            &lt;mxPoint x=\&quot;560\&quot; y=\&quot;292\&quot; as=\&quot;targetPoint\&quot; /&gt;\n            &lt;Array as=\&quot;points\&quot;&gt;\n              &lt;mxPoint x=\&quot;575\&quot; y=\&quot;296\&quot; /&gt;\n            &lt;/Array&gt;\n          &lt;/mxGeometry&gt;\n        &lt;/mxCell&gt;\n      &lt;/root&gt;\n    &lt;/mxGraphModel&gt;\n  &lt;/diagram&gt;\n&lt;/mxfile&gt;\n&quot;}"></div>
<script type="text/javascript" src="https://viewer.diagrams.net/js/viewer-static.min.js"></script>

{% info_block warningBox "Info" %}

Depending on the update status of your SCOS module versions, the type of actions and associated effort to make your project ACP-ready may vary. However, the task of making your proejct ACP-enabled is always handled by Spryker.

{% endinfo_block %}

## Getting SCOS ACP-ready

Getting your project ACP-Ready requires different update steps depending on the template version on which your project was started:

- SCOS product release [202211.0](/docs/scos/user/intro-to-spryker/releases/release-notes/release-notes-202211.0/release-notes-202211.0.html): All changes are included to have the project ACP-ready, however they need to be verified on the project level.
- Older versions: All steps required to get the project ACP-ready.

{% info_block infoBox "Product version ealier than 202211.0" %}

If you were onboarded with a version older than product release [202211.0](/docs/scos/user/intro-to-spryker/releases/release-notes/release-notes-202211.0/release-notes-202211.0.html), please [contact us](https://support.spryker.com/). 

{% endinfo_block %}

### 1. Module updates for ACP

To get your project ACP-ready, you should make sure that your project modules are updated to the necessary versions.

#### 1. ACP modules

The ACP catalog is included by default to the Spryker Cloud product starting with the Spryker Product Release [202211.0](/docs/scos/user/intro-to-spryker/releases/release-notes/release-notes-202211.0/release-notes-202211.0.html). 

However, in any case youe should make sure that your Spryker project uses the latest versions of the following modules:

* `spryker/app-catalog-gui: ^1.2.0` or higher
* `spryker/message-broker:^1.4.0` or higher
* `spryker/message-broker-aws:^1.3.2` or higher
* `spryker/session:^4.15.1` or higher

#### 2. App modules

{% info_block warningBox "Apps- and PBC-specific modules" %}

Depending on the specific ACP apps or [PBCs](/docs/pbc/all/pbc.html) you would like to use via ACP, you have to add or update the modules for each respective app or PBC as detailed in the guide for each app.

{% endinfo_block %}

The Spryker ACP Apps are continously extended and improved with new versions. Though you don't have to update the apps themselves, it might be at times necessary to perform minor updates of the app-related SCOS modules to take full advantage of the latest app feature updates.

For each app you want to use, ensure you have the latest app-related SCOS modules installed. The following apps are supported:

- [Algolia](/docs/pbc/all/search/{{site.version}}/third-party-integrations/algolia.html), a Search Engine
- [Payone](/docs/pbc/all/payment-service-providers/payone/payone.html), a Payment Service Provider (PSP)
- [Usercentrics](/docs/pbc/all/usercentrics/usercentrics.html), a Consent Management Platform (CMP)
- [Bazaarvoice](/docs/pbc/all/ratings-reviews/{{site.version}}/third-party-integrations/bazaarvoice.html), a platform for User-Generated Content (UGC)

### 2. Configure SCOS

Having making sure that your project modules are up-to-date, configure your SCOS projec to activate the ACP catalog in the Back Office as follows:

1. Define the configuration and add plugins to the following files:

<details open>
<summary>config/Shared/config_default.php</summary>

```php
use Spryker\Shared\AppCatalogGui\AppCatalogGuiConstants;
use Spryker\Shared\Kernel\KernelConstants;
use Spryker\Shared\MessageBroker\MessageBrokerConstants;
use Spryker\Shared\MessageBrokerAws\MessageBrokerAwsConstants;
use Spryker\Shared\OauthAuth0\OauthAuth0Constants;
use Spryker\Shared\OauthClient\OauthClientConstants;
use Spryker\Shared\Store\StoreConstants;
use Spryker\Zed\OauthAuth0\OauthAuth0Config;

...

// ----------------------------------------------------------------------------
// ------------------------------ ACP -----------------------------------------
// ----------------------------------------------------------------------------
$aopApplicationConfiguration = json_decode(html_entity_decode((string)getenv('SPRYKER_AOP_APPLICATION')), true);
$config[KernelConstants::DOMAIN_WHITELIST] = array_merge(
    $config[KernelConstants::DOMAIN_WHITELIST],
    $aopApplicationConfiguration['APP_DOMAINS'] ?? [],
);
$config[StoreConstants::STORE_NAME_REFERENCE_MAP] = $aopApplicationConfiguration['STORE_NAME_REFERENCE_MAP'] ?? [];
$config[AppCatalogGuiConstants::APP_CATALOG_SCRIPT_URL] = $aopApplicationConfiguration['APP_CATALOG_SCRIPT_URL'] ?? '';

$aopAuthenticationConfiguration = json_decode(html_entity_decode((string)getenv('SPRYKER_AOP_AUTHENTICATION')), true);
$config[OauthAuth0Constants::AUTH0_CUSTOM_DOMAIN] = $aopAuthenticationConfiguration['AUTH0_CUSTOM_DOMAIN'] ?? '';
$config[OauthAuth0Constants::AUTH0_CLIENT_ID] = $aopAuthenticationConfiguration['AUTH0_CLIENT_ID'] ?? '';
$config[OauthAuth0Constants::AUTH0_CLIENT_SECRET] = $aopAuthenticationConfiguration['AUTH0_CLIENT_SECRET'] ?? '';

$config[MessageBrokerConstants::CHANNEL_TO_TRANSPORT_MAP] =
$config[MessageBrokerAwsConstants::CHANNEL_TO_RECEIVER_TRANSPORT_MAP] = [
    // Here we will define the receiver transport map accordinally to APP (PBC)
];

$config[MessageBrokerAwsConstants::CHANNEL_TO_SENDER_TRANSPORT_MAP] = [
    // Here we will define the sender transport map accordinally to APP (PBC)
];

$aopInfrastructureConfiguration = json_decode(html_entity_decode((string)getenv('SPRYKER_AOP_INFRASTRUCTURE')), true);

$config[MessageBrokerAwsConstants::SQS_RECEIVER_CONFIG] = json_encode($aopInfrastructureConfiguration['SPRYKER_MESSAGE_BROKER_SQS_RECEIVER_CONFIG'] ?? []);
$config[MessageBrokerAwsConstants::HTTP_SENDER_CONFIG] = $aopInfrastructureConfiguration['SPRYKER_MESSAGE_BROKER_HTTP_SENDER_CONFIG'] ?? [];

// ----------------------------------------------------------------------------
// ------------------------------ OAUTH ---------------------------------------
// ----------------------------------------------------------------------------
$config[OauthClientConstants::OAUTH_PROVIDER_NAME_FOR_MESSAGE_BROKER] = OauthAuth0Config::PROVIDER_NAME;
$config[OauthClientConstants::OAUTH_GRANT_TYPE_FOR_MESSAGE_BROKER] = OauthAuth0Config::GRANT_TYPE_CLIENT_CREDENTIALS;
$config[OauthClientConstants::OAUTH_OPTION_AUDIENCE_FOR_MESSAGE_BROKER] = 'aop-event-platform';

$config[AppCatalogGuiConstants::OAUTH_PROVIDER_NAME] = OauthAuth0Config::PROVIDER_NAME;
$config[AppCatalogGuiConstants::OAUTH_GRANT_TYPE] = OauthAuth0Config::GRANT_TYPE_CLIENT_CREDENTIALS;
$config[AppCatalogGuiConstants::OAUTH_OPTION_AUDIENCE] = 'aop-atrs';

$config[OauthClientConstants::OAUTH_PROVIDER_NAME_FOR_PAYMENT_AUTHORIZE] = OauthAuth0Config::PROVIDER_NAME;
$config[OauthClientConstants::OAUTH_GRANT_TYPE_FOR_PAYMENT_AUTHORIZE] = OauthAuth0Config::GRANT_TYPE_CLIENT_CREDENTIALS;
$config[OauthClientConstants::OAUTH_OPTION_AUDIENCE_FOR_PAYMENT_AUTHORIZE] = 'aop-app';
```
</details>

2. Add one more navigation items to the navigation.xml file:

<details open>
<summary>config/Zed/navigation.xml</summary>

```xml
...
  <app-catalog-gui>
      <label>Apps</label>
      <title>Apps</title>
      <icon>fa-cubes</icon>
      <bundle>app-catalog-gui</bundle>
      <controller>index</controller>
      <action>index</action>
  </app-catalog-gui>
...    
```
</details>

3. In the `MessageBrokerDependencyProvider.php` file, enable the following module plugins:

<details open>
<summary>src/Pyz/Zed/MessageBroker/MessageBrokerDependencyProvider.php</summary>

```php
<?php

/**
 * This file is part of the Spryker Suite.
 * For full license information, please view the LICENSE file that was distributed with this source code.
 */

namespace Pyz\Zed\MessageBroker;

use Spryker\Zed\MessageBroker\Communication\Plugin\MessageBroker\CorrelationIdMessageAttributeProviderPlugin;
use Spryker\Zed\MessageBroker\Communication\Plugin\MessageBroker\TimestampMessageAttributeProviderPlugin;
use Spryker\Zed\MessageBroker\Communication\Plugin\MessageBroker\TransactionIdMessageAttributeProviderPlugin;
use Spryker\Zed\MessageBroker\Communication\Plugin\MessageBroker\ValidationMiddlewarePlugin;
use Spryker\Zed\MessageBroker\MessageBrokerDependencyProvider as SprykerMessageBrokerDependencyProvider;
use Spryker\Zed\MessageBrokerAws\Communication\Plugin\MessageBroker\Receiver\AwsSqsMessageReceiverPlugin;
use Spryker\Zed\MessageBrokerAws\Communication\Plugin\MessageBroker\Sender\AwsSnsMessageSenderPlugin;
use Spryker\Zed\MessageBrokerAws\Communication\Plugin\MessageBroker\Sender\AwsSqsMessageSenderPlugin;
use Spryker\Zed\MessageBrokerAws\Communication\Plugin\MessageBroker\Sender\HttpMessageSenderPlugin;
use Spryker\Zed\OauthClient\Communication\Plugin\MessageBroker\AccessTokenMessageAttributeProviderPlugin;
use Spryker\Zed\Session\Communication\Plugin\MessageBroker\SessionTrackingIdMessageAttributeProviderPlugin;
use Spryker\Zed\Store\Communication\Plugin\MessageBroker\CurrentStoreReferenceMessageAttributeProviderPlugin;
use Spryker\Zed\Store\Communication\Plugin\MessageBroker\StoreReferenceMessageValidatorPlugin;

class MessageBrokerDependencyProvider extends SprykerMessageBrokerDependencyProvider
{
    /**
     * @return array<\Spryker\Zed\MessageBrokerExtension\Dependency\Plugin\MessageSenderPluginInterface>
     */
    public function getMessageSenderPlugins(): array
    {
        return [
            new AwsSnsMessageSenderPlugin(),
            new AwsSqsMessageSenderPlugin(),
            new HttpMessageSenderPlugin(),
        ];
    }

    /**
     * @return array<\Spryker\Zed\MessageBrokerExtension\Dependency\Plugin\MessageReceiverPluginInterface>
     */
    public function getMessageReceiverPlugins(): array
    {
        return [
            new AwsSqsMessageReceiverPlugin(),
        ];
    }

    /**
     * @return array<\Spryker\Zed\MessageBrokerExtension\Dependency\Plugin\MessageAttributeProviderPluginInterface>
     */
    public function getMessageAttributeProviderPlugins(): array
    {
        return [
            new CorrelationIdMessageAttributeProviderPlugin(),
            new TimestampMessageAttributeProviderPlugin(),
            new CurrentStoreReferenceMessageAttributeProviderPlugin(),
            new AccessTokenMessageAttributeProviderPlugin(),
            new TransactionIdMessageAttributeProviderPlugin(),
            new SessionTrackingIdMessageAttributeProviderPlugin(),
        ];
    }

    /**
     * @return array<\Spryker\Zed\MessageBrokerExtension\Dependency\Plugin\MiddlewarePluginInterface>
     */
    public function getMiddlewarePlugins(): array
    {
        return [
            new ValidationMiddlewarePlugin(),
        ];
    }

    /**
     * @return array<\Spryker\Zed\MessageBrokerExtension\Dependency\Plugin\MessageValidatorPluginInterface>
     */
    public function getExternalValidatorPlugins(): array
    {
        return [
            new StoreReferenceMessageValidatorPlugin(),
        ];
    }
}
```
</details>

4. In the `MessageBrokerConfig.php` file, adjust the following module config:

<details open>
<summary>src/Pyz/Zed/MessageBroker/MessageBrokerConfig.php</summary>

```php
<?php

/**
 * This file is part of the Spryker Suite.
 * For full license information, please view the LICENSE file that was distributed with this source code.
 */

namespace Pyz\Zed\MessageBroker;

use Generated\Shared\Transfer\MessageAttributesTransfer;
use Spryker\Zed\MessageBroker\MessageBrokerConfig as SprykerMessageBrokerConfig;

class MessageBrokerConfig extends SprykerMessageBrokerConfig
{
    /**
     * Defines attributes which should not be logged.
     *
     * @api
     *
     * @return array<string>
     */
    public function getProtectedMessageAttributes(): array
    {
        return [
            MessageAttributesTransfer::AUTHORIZATION,
        ];
    }
}
```
</details>

5. In the `OauthClientDependencyProvider.php` file, enable the following module plugins:

In the MessageBrokerConfig.php, adjust the following module config:
<details open>
<summary>src/Pyz/Zed/OauthClient/OauthClientDependencyProvider.php</summary>

```php
<?php

/**
 * This file is part of the Spryker Suite.
 * For full license information, please view the LICENSE file that was distributed with this source code.
 */

namespace Pyz\Zed\OauthClient;

use Spryker\Zed\OauthAuth0\Communication\Plugin\OauthClient\Auth0OauthAccessTokenProviderPlugin;
use Spryker\Zed\OauthClient\OauthClientDependencyProvider as SprykerOauthClientDependencyProvider;
use Spryker\Zed\OauthDummy\Communication\Plugin\OauthClient\DummyOauthAccessTokenProviderPlugin;
use Spryker\Zed\Store\Communication\Plugin\OauthClient\CurrentStoreReferenceAccessTokenRequestExpanderPlugin;

class OauthClientDependencyProvider extends SprykerOauthClientDependencyProvider
{
    /**
     * @return array<\Spryker\Zed\OauthClientExtension\Dependency\Plugin\OauthAccessTokenProviderPluginInterface>
     */
    protected function getOauthAccessTokenProviderPlugins(): array
    {
        return [
            new DummyOauthAccessTokenProviderPlugin(),
            new Auth0OauthAccessTokenProviderPlugin(),
        ];
    }

    /**
     * @return array<\Spryker\Zed\OauthClientExtension\Dependency\Plugin\AccessTokenRequestExpanderPluginInterface>
     */
    protected function getAccessTokenRequestExpanderPlugins(): array
    {
        return [
            new CurrentStoreReferenceAccessTokenRequestExpanderPlugin(),
        ];
    }
}
```
</details>

### 3. Update the SCOS deploy.yml file

This section describes the variables that you must configure for the use within your SCOS AWS environment.

You need to define the environment variables in the `deploy.yml` file of *each* SCOS environment like testing, staging, production.

There will be multiple general environment variables that in turn will contain several configurations. 

{% info_block warningBox "Warning" %}

You must specify the environment variable keys. The infrastructure values (FIFO queue names) are provided by the Spryker Ops upon request.

{% endinfo_block %}

<details open>
<summary>General structure</summary>

```json
ENVIRONMENT_VARIABLE_NAME_A:{
  "CONFIGURATION_KEY_A":"SOME_VALUE_A",
  "CONFIGURATION_KEY_B":"SOME_VALUE_B"
}
```
</details>

<details open>
<summary>Data structure example for a demo environment connected to the Spryker ACP production</summary>

```json
#AOP
SPRYKER_AOP_APPLICATION: '{
  "APP_CATALOG_SCRIPT_URL": "https://app-catalog.atrs.spryker.com/loader",
  "STORE_NAME_REFERENCE_MAP": {"DE": "tenant_messages_for_store_reference_AOP_Demo_Production-DE.fifo", "AT": "tenant_messages_for_store_reference_AOP_Demo_Production-AT.fifo"},
  "APP_DOMAINS": [
      "os.apps.aop.spryker.com",
      "*.bazaarvoice.com"
  ]
}'

SPRYKER_AOP_INFRASTRUCTURE: '{
  "SPRYKER_MESSAGE_BROKER_HTTP_SENDER_CONFIG": {
        "endpoint":"https:\/\/events.atrs.spryker.com\/events\/tenant"
  },
  "SPRYKER_MESSAGE_BROKER_SQS_RECEIVER_CONFIG": {
    "default": {
        "endpoint":"https:\/\/sqs.eu-central-1.amazonaws.com",
        "region":"eu-central-1",
        "auto_setup":false,
        "buffer_size":1
    },
      "DE": {
        "queue_name":"tenant_messages_for_store_reference_AOP_Demo_Production-DE.fifo"
    },
    "AT": {
        "queue_name":"tenant_messages_for_store_reference_AOP_Demo_Production-AT.fifo"
    }
  }
}'
```
</details>

#### General configurations

<div class="width-100">

<table class="tg">
<thead>
  <tr>
    <th>Variable</th>
    <th>Configuration key</th>
    <th>Desctiption</th>
    <th>Example</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td rowspan="3">SPRYKER_AOP_APPLICATION</td>
    <td>APP_CATALOG_SCRIPT_URL</td>
    <td>URL for the App-Tenant-Registry-Service (ATRS) and path to the JS script to load the ACP catalog</td>
    <td>Production ATRS_HOST and path:
    <pre>
    json
    https://app-catalog.atrs.spryker.com/loader
    </pre>
    </td>
  </tr>
  <tr>
    <td>STORE_NAME_REFERENCE_MAP</td>
    <td>StoreReference mapping to the appropriate Spryker Store</td>
    <td>Demo Stores for DE and AT: 
    <pre>
    json 
    {"DE": "tenant_messages_for_store_reference_AOP_Demo_Production-DE", "AT": "tenant_messages_for_store_reference_AOP_Demo_Production-AT"}
    </pre></td>
  </tr>
  <tr>
    <td>APP_DOMAINS</td>
    <td>App domains used in redirects.</td>
    <td><pre>json
    [
      "os.apps.aop.spryker.com",
      "*.bazaarvoice.com"
    ]</pre>
</td>
  </tr>
</tbody>
</table>

</div>

#### Message Broker configuration

<div class="width-100">

<table class="tg">
<thead>
  <tr>
    <th>Variable</th>
    <th>Configuration key</th>
    <th>Desctiption</th>
    <th>Example</th>
  </tr>
</thead>
<tbody>
  <tr>
    <td rowspan="2">SPRYKER_AOP_INFRASTRUCTURE</td>
    <td>SPRYKER_MESSAGE_BROKER_SQS_RECEIVER_CONFIG</td>
    <td>Receiver configuration. The queues must be defined for each store (or default queue for all stores is used)
{% info_block warningBox "Warning" %}

Queues will be created by Spryker Ops and values provided by them for you to add!

{% endinfo_block %}
</td>
    <td>Example from the Spryker Production environment:
    <pre>json
{
  "default": {
    "endpoint":"https://sqs.eu-central-1.amazonaws.com",
    "auto_setup":false, "buffer_size":1
  },
  "DE": {
    "queue_name":"tenant_messages_for_store_reference_AOP_Demo_Production-DE.fifo"
  },
  &quot;&lt;Store&gt;&quot;: {
    "queue_name":"queue_name_for_store_reference_&quot;&lt;Store&gt;&quot;"
  }
}
</pre>
  </td>
</tr>
  <tr>
    <td>SPRYKER_MESSAGE_BROKER_HTTP_SENDER_CONFIG</td>
    <td>StoreReference mapping to the appropriate Spryker Store</td>
    <td>Example from the Spryker Production environment:
    <pre>json
    {
    "endpoint":"https://events.atrs.spryker.com/events/tenant"
    }
    </pre>
    </td>
  </tr>
</tbody>
</table>

</div>

## Next steps after the ACP-readiness

After configuring the files, updating all modules, and adding the requested keys with their corresponding values provided by Spryker Ops to the deploy.yml file, the SCOS codebase is now up-to-date. Once redeployed, your environment will be ACP-ready.

The next step is to get your newly updated and deployed ACP-ready SCOS environment ACP-enabled. The ACP enablement step is fully handled by Spryker and implies registration of your ACP-ready SCOS environment with ACP by connecting it with the ACP App-Tenant-Registry-Service (ATRS) as well as the Event Platform (EP), so that the ACP Catalog is able to work with SCOS.

To get you project ACP-enabled, contact the [Spryker support](https://spryker.com/support/).

Once all the steps of the ACP-enablement process are completed, the ACP catalog appears in the Back Office:

![acp-catalog](https://spryker.s3.eu-central-1.amazonaws.com/docs/aop/app-orchestration-platform-overview/aop-catalog.png)