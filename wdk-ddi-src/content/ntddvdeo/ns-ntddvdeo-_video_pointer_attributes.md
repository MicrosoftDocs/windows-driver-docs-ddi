---
UID: NS:ntddvdeo._VIDEO_POINTER_ATTRIBUTES
title: "_VIDEO_POINTER_ATTRIBUTES"
author: windows-driver-content
description: The VIDEO_POINTER_ATTRIBUTES structure contains attributes of the screen pointer.
old-location: display\video_pointer_attributes.htm
old-project: display
ms.assetid: aa897435-443b-4145-b6ca-7bafdb36b9c1
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: VIDEO_POINTER_ATTRIBUTES, PVIDEO_POINTER_ATTRIBUTES, VIDEO_POINTER_ATTRIBUTES structure [Display Devices], VIDEO_MODE_ASYNC_POINTER, VIDEO_MODE_ANIMATE_START, _VIDEO_POINTER_ATTRIBUTES, *PVIDEO_POINTER_ATTRIBUTES, ntddvdeo/VIDEO_POINTER_ATTRIBUTES, PVIDEO_POINTER_ATTRIBUTES structure pointer [Display Devices], display.video_pointer_attributes, VIDEO_MODE_MONO_POINTER, Video_Structs_5ade2674-a930-46b3-aaad-6d3a8d017453.xml, VIDEO_MODE_ANIMATE_UPDATE, VIDEO_MODE_COLOR_POINTER, ntddvdeo/PVIDEO_POINTER_ATTRIBUTES
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddvdeo.h
apiname:
-	VIDEO_POINTER_ATTRIBUTES
product: Windows
targetos: Windows
req.typenames: "*PVIDEO_POINTER_ATTRIBUTES, VIDEO_POINTER_ATTRIBUTES"
---

# _VIDEO_POINTER_ATTRIBUTES structure


## -description


The VIDEO_POINTER_ATTRIBUTES structure contains attributes of the screen pointer.


## -syntax


````
typedef struct _VIDEO_POINTER_ATTRIBUTES {
  ULONG Flags;
  ULONG Width;
  ULONG Height;
  ULONG WidthInBytes;
  ULONG Enable;
  SHORT Column;
  SHORT Row;
  UCHAR Pixels[1];
} VIDEO_POINTER_ATTRIBUTES, *PVIDEO_POINTER_ATTRIBUTES;
````


## -struct-fields




### -field Flags

A set of flags that specify certain attributes of the pointer. <b>Flags</b> can be a combination of the following values:
<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="VIDEO_MODE_ASYNC_POINTER"></a><a id="video_mode_async_pointer"></a><dl>
<dt><b>VIDEO_MODE_ASYNC_POINTER</b></dt>
</dl>
</td>
<td width="60%">
The pointer can be updated asynchronously to drawing operations.

</td>
</tr>
<tr>
<td width="40%"><a id="VIDEO_MODE_MONO_POINTER"></a><a id="video_mode_mono_pointer"></a><dl>
<dt><b>VIDEO_MODE_MONO_POINTER</b></dt>
</dl>
</td>
<td width="60%">
A monochrome hardware pointer is supported.

</td>
</tr>
<tr>
<td width="40%"><a id="VIDEO_MODE_COLOR_POINTER"></a><a id="video_mode_color_pointer"></a><dl>
<dt><b>VIDEO_MODE_COLOR_POINTER</b></dt>
</dl>
</td>
<td width="60%">
A color hardware pointer is supported.

</td>
</tr>
<tr>
<td width="40%"><a id="VIDEO_MODE_ANIMATE_START"></a><a id="video_mode_animate_start"></a><dl>
<dt><b>VIDEO_MODE_ANIMATE_START</b></dt>
</dl>
</td>
<td width="60%">
The current pointer has the same hotspot as the previous pointer.

</td>
</tr>
<tr>
<td width="40%"><a id="VIDEO_MODE_ANIMATE_UPDATE"></a><a id="video_mode_animate_update"></a><dl>
<dt><b>VIDEO_MODE_ANIMATE_UPDATE</b></dt>
</dl>
</td>
<td width="60%">
The current pointer has the same hotspot as the previous pointer.

</td>
</tr>
</table> 


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

<a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_set_pointer_attr.md">IOCTL_VIDEO_SET_POINTER_ATTR</a>

<a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_query_pointer_attr.md">IOCTL_VIDEO_QUERY_POINTER_ATTR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VIDEO_POINTER_ATTRIBUTES structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

