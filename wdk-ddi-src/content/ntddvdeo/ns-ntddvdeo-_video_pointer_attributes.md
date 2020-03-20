---
UID: NS:ntddvdeo._VIDEO_POINTER_ATTRIBUTES
title: _VIDEO_POINTER_ATTRIBUTES (ntddvdeo.h)
description: The VIDEO_POINTER_ATTRIBUTES structure contains attributes of the screen pointer.
old-location: display\video_pointer_attributes.htm
tech.root: display
ms.assetid: aa897435-443b-4145-b6ca-7bafdb36b9c1
ms.date: 05/10/2018
keywords: ["_VIDEO_POINTER_ATTRIBUTES structure"]
ms.keywords: "*PVIDEO_POINTER_ATTRIBUTES, PVIDEO_POINTER_ATTRIBUTES, PVIDEO_POINTER_ATTRIBUTES structure pointer [Display Devices], VIDEO_MODE_ANIMATE_START, VIDEO_MODE_ANIMATE_UPDATE, VIDEO_MODE_ASYNC_POINTER, VIDEO_MODE_COLOR_POINTER, VIDEO_MODE_MONO_POINTER, VIDEO_POINTER_ATTRIBUTES, VIDEO_POINTER_ATTRIBUTES structure [Display Devices], Video_Structs_5ade2674-a930-46b3-aaad-6d3a8d017453.xml, _VIDEO_POINTER_ATTRIBUTES, display.video_pointer_attributes, ntddvdeo/PVIDEO_POINTER_ATTRIBUTES, ntddvdeo/VIDEO_POINTER_ATTRIBUTES"
f1_keywords:
 - "ntddvdeo/VIDEO_POINTER_ATTRIBUTES"
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
- ntddvdeo.h
api_name:
- VIDEO_POINTER_ATTRIBUTES
product:
- Windows
targetos: Windows
req.typenames: VIDEO_POINTER_ATTRIBUTES, *PVIDEO_POINTER_ATTRIBUTES
---

# _VIDEO_POINTER_ATTRIBUTES structure


## -description


The VIDEO_POINTER_ATTRIBUTES structure contains attributes of the screen pointer.


## -struct-fields




### -field Flags

A set of flags that specify certain attributes of the pointer. <b>Flags</b> can be a combination of the following values:
|Value|Meaning|
|--- |--- |
|VIDEO_MODE_ASYNC_POINTER|The pointer can be updated asynchronously to drawing operations.|
|VIDEO_MODE_MONO_POINTER|A monochrome hardware pointer is supported.|
|VIDEO_MODE_COLOR_POINTER|A color hardware pointer is supported.|
|VIDEO_MODE_ANIMATE_START|The current pointer has the same hotspot as the previous pointer.|
|VIDEO_MODE_ANIMATE_UPDATE|The current pointer has the same hotspot as the previous pointer.|

### -field Width

Specifies the width of the pointer in pixels.


### -field Height

Specifies the height of the pointer in pixels.


### -field WidthInBytes

Specifies the width of the pointer in bytes.


### -field Enable

Specifies whether the pointer is visible. A nonzero value specifies that the pointer is visible. A value of zero specifies that the pointer is not visible.


### -field Column

Horizontal coordinate of the pointer's hot spot.


### -field Row

Vertical coordinate of the pointer's hot spot.


### -field Pixels

The pointer data, in device-compatible DIB format. Mask data is always in 1-bpp DIB format.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvdeo/ni-ntddvdeo-ioctl_video_query_pointer_attr">IOCTL_VIDEO_QUERY_POINTER_ATTR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvdeo/ni-ntddvdeo-ioctl_video_set_pointer_attr">IOCTL_VIDEO_SET_POINTER_ATTR</a>
 

 

