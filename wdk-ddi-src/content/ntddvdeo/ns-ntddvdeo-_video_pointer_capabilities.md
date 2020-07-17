---
UID: NS:ntddvdeo._VIDEO_POINTER_CAPABILITIES
title: _VIDEO_POINTER_CAPABILITIES (ntddvdeo.h)
description: Contains capabilities of the screen pointer.
old-location: display\video_pointer_capabilities.htm
tech.root: display
ms.assetid: bc5f98da-1e2e-421b-9c76-97359e51b526
ms.date: 05/10/2018
keywords: ["_VIDEO_POINTER_CAPABILITIES structure"]
ms.keywords: "*PVIDEO_POINTER_CAPABILITIES, PVIDEO_POINTER_CAPABILITIES, PVIDEO_POINTER_CAPABILITIES structure pointer [Display Devices], VIDEO_POINTER_CAPABILITIES, VIDEO_POINTER_CAPABILITIES structure [Display Devices], Video_Structs_03a35602-adfd-4485-a155-866b578fa807.xml, _VIDEO_POINTER_CAPABILITIES, display.video_pointer_capabilities, ntddvdeo/PVIDEO_POINTER_CAPABILITIES, ntddvdeo/VIDEO_POINTER_CAPABILITIES"
f1_keywords:
 - "ntddvdeo/VIDEO_POINTER_CAPABILITIES"
 - "VIDEO_POINTER_CAPABILITIES"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddvdeo.h
api_name:
- VIDEO_POINTER_CAPABILITIES
product:
- Windows
targetos: Windows
req.typenames: VIDEO_POINTER_CAPABILITIES, *PVIDEO_POINTER_CAPABILITIES
---

# _VIDEO_POINTER_CAPABILITIES structure


## -description


The <b>VIDEO_POINTER_CAPABILITIES</b> structure contains capabilities of the screen pointer.


## -struct-fields




### -field Flags

A set of flags that specify certain capabilities of the pointer. Flags can be a combination of the following values.

|Flag|Meaning|
|--- |--- |
|VIDEO_MODE_ASYNC_POINTER|The pointer can be updated asynchronously to drawing operations.|
|VIDEO_MODE_MONO_POINTER|A monochrome hardware pointer is supported.|
|VIDEO_MODE_COLOR_POINTER|A color hardware pointer is supported.|
|VIDEO_MODE_ANIMATE_START|The current pointer has the same hotspot as the previous pointer.|
|VIDEO_MODE_ANIMATE_UPDATE|The current pointer has the same hotspot as the previous pointer.|

### -field MaxWidth

Specifies the maximum width of the pointer, in pixels.


### -field MaxHeight

Specifies the maximum height of the pointer, in pixels.


### -field HWPtrBitmapStart

Specifies the first offset, in CPU-addressable units, in the memory bitmap that is used to store the hardware pointer bitmap. A value of –1 is not valid.


### -field HWPtrBitmapEnd

Specifies the last offset, in CPU-addressable units, in the memory bitmap that is used to store the hardware pointer bitmap. A value of –1 is not valid.

