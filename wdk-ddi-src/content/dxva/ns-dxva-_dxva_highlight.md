---
UID: NS:dxva._DXVA_Highlight
title: "_DXVA_Highlight"
author: windows-driver-content
description: The DXVA_Highlight structure is sent by the host decoder to the accelerator to specify a highlighted rectangular area of a subpicture, and to create an alpha-blending surface with DCCMD data and a DPXD surface.
old-location: display\dxva_highlight.htm
old-project: display
ms.assetid: 62c5f41a-1db2-4777-af86-67d2345a05c0
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: "*LPDXVA_Highlight, DXVA_Highlight, DXVA_Highlight structure [Display Devices], LPDXVA_Highlight, LPDXVA_Highlight structure pointer [Display Devices], _DXVA_Highlight, display.dxva_highlight, dxva/DXVA_Highlight, dxva/LPDXVA_Highlight, dxvaref_509ed85b-59ad-44d2-a686-2b2077542c6d.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	dxva.h
api_name:
-	DXVA_Highlight
product:
- Windows
targetos: Windows
req.typenames: DXVA_Highlight, *LPDXVA_Highlight
---

# _DXVA_Highlight structure


## -description


The DXVA_Highlight structure is sent by the host decoder to the accelerator to specify a highlighted rectangular area of a subpicture, and to create an alpha-blending surface with DCCMD data and a DPXD surface.


## -struct-fields




### -field wHighlightActive

Indicates whether a rectangular highlight area is active. Zero indicates inactive and 1 indicates active. If inactive, the highlight data must have no effect on the content of the blended picture.


### -field wHighlightIndices

Contains four palette indexes. Each palette index consists of 4 bits. Each 2-bit index in the highlighted rectangular area of the DXPD is used to select among these four palette indexes. The 4 most significant bits are for index 3, the next 4 bits are for index 2, the next 4 bits are for index 1, and the 4 least significant bits are for index 0. 


### -field wHighlightAlphas

Contains four opacity values. Each opacity value consists of 4 bits. Each 2-bit index in the highlighted rectangular area of the DXPD is used to select among these four opacity values. The 4 most significant bits are for index 3, the next 4 bits are for index 2, the next 4 bits are for index 1, and the 4 least significant bits are for index 0.

These 4-bit opacity values are each referred to as a <i>SampleAlpha4</i> variable and are interpreted as follows:

<ul>
<li>
The value zero indicates that the graphic content at the corresponding location is transparent (so that the palette entry indexed by the corresponding bits of <b>wHighlightIndices</b> has no effect on the resulting blended picture). For a zero value, the blend specified is to use the video picture content without alteration.

</li>
<li>
The value 15 indicates that the graphic content at the corresponding location is opaque (so that the palette entry indexed by the corresponding bits of <b>wHighlightIndices</b> completely determines the resulting blended picture).

</li>
<li>
For nonzero values, the specified blend is found using the following expression:

</li>
<li>
( ( ( (<i>SampleAlpha4</i> + 1) x (graphic value) ) + ( ( (15 - <i>SampleAlpha4</i>) x (picture value) ) + 8 ) &gt;&gt; 4

</li>
</ul>

### -field HighlightRect

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that defines the area of the highlight rectangle.

The following restrictions apply to the RECT dimensions:

<ul>
<li>
<b>left</b> and <b>top</b> must be greater than or equal to zero.

</li>
<li>
<b>right</b> and <b>bottom</b> must be greater than <b>left</b> and <b>top</b>, respectively.

</li>
<li>
<b>right</b> must not exceed 720, and <b>bottom</b> must not exceed 576.

</li>
</ul>

## -remarks



The DXVA_Highlight structure is formulated in a manner compatible with the DVD video specification as specified by the DVD Forum.

<div class="alert"><b>Note</b>    There is a difference between the way the DVD specification defines a subpicture rectangular area and the convention used by Microsoft. This section follows the Microsoft convention so a rectangle of width 10 and height 10 in the upper-left corner of the picture is defined by <b>top</b> = 0, <b>left</b> = 0, <b>right</b> = 10, <b>bottom</b> = 10. The DVD specification defines <b>right</b> = 9 and <b>bottom</b> = 9.</div>
<div> </div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>
 

 

