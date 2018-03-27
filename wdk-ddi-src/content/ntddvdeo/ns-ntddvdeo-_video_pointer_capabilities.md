---
UID: NS:ntddvdeo._VIDEO_POINTER_CAPABILITIES
title: "_VIDEO_POINTER_CAPABILITIES"
author: windows-driver-content
description: Contains capabilities of the screen pointer.
old-location: display\video_pointer_capabilities.htm
old-project: display
ms.assetid: bc5f98da-1e2e-421b-9c76-97359e51b526
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PVIDEO_POINTER_CAPABILITIES, PVIDEO_POINTER_CAPABILITIES, PVIDEO_POINTER_CAPABILITIES structure pointer [Display Devices], VIDEO_POINTER_CAPABILITIES, VIDEO_POINTER_CAPABILITIES structure [Display Devices], Video_Structs_03a35602-adfd-4485-a155-866b578fa807.xml, _VIDEO_POINTER_CAPABILITIES, display.video_pointer_capabilities, ntddvdeo/PVIDEO_POINTER_CAPABILITIES, ntddvdeo/VIDEO_POINTER_CAPABILITIES"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddvdeo.h
req.include-header: Ntddvdeo.h
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
-	Ntddvdeo.h
api_name:
-	VIDEO_POINTER_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: VIDEO_POINTER_CAPABILITIES, *PVIDEO_POINTER_CAPABILITIES
---

# _VIDEO_POINTER_CAPABILITIES structure


## -description


The <b>VIDEO_POINTER_CAPABILITIES</b> structure contains capabilities of the screen pointer.


## -struct-fields




### -field Flags

A set of flags that specify certain capabilities of the pointer. Flags can be a combination of the following values.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
VIDEO_MODE_ASYNC_POINTER

</td>
<td>
The pointer can be updated asynchronously to drawing operations.

</td>
</tr>
<tr>
<td>
VIDEO_MODE_MONO_POINTER

</td>
<td>
A monochrome hardware pointer is supported.

</td>
</tr>
<tr>
<td>
VIDEO_MODE_COLOR_POINTER

</td>
<td>
A color hardware pointer is supported.

</td>
</tr>
<tr>
<td>
VIDEO_MODE_ANIMATE_START

</td>
<td>
The current pointer has the same hotspot as the previous pointer.

</td>
</tr>
<tr>
<td>
VIDEO_MODE_ANIMATE_UPDATE

</td>
<td>
The current pointer has the same hotspot as the previous pointer.

</td>
</tr>
</table>
 


### -field MaxWidth

Specifies the maximum width of the pointer, in pixels.


### -field MaxHeight

Specifies the maximum height of the pointer, in pixels.


### -field HWPtrBitmapStart

Specifies the first offset, in CPU-addressable units, in the memory bitmap that is used to store the hardware pointer bitmap. A value of –1 is not valid.


### -field HWPtrBitmapEnd

Specifies the last offset, in CPU-addressable units, in the memory bitmap that is used to store the hardware pointer bitmap. A value of –1 is not valid.

