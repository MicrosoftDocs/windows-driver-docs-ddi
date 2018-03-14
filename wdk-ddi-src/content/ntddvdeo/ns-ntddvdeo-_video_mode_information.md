---
UID: NS:ntddvdeo._VIDEO_MODE_INFORMATION
title: "_VIDEO_MODE_INFORMATION"
author: windows-driver-content
description: The VIDEO_MODE_INFORMATION structure contains all of the information about one mode of a video adapter.
old-location: display\video_mode_information.htm
old-project: display
ms.assetid: aac658d9-b90a-4724-9dc4-af3a561f64bd
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PVIDEO_MODE_INFORMATION, PVIDEO_MODE_INFORMATION, PVIDEO_MODE_INFORMATION structure pointer [Display Devices], VIDEO_MODE_INFORMATION, VIDEO_MODE_INFORMATION structure [Display Devices], Video_Structs_76f182b8-be55-42d0-948f-29e05e956895.xml, _VIDEO_MODE_INFORMATION, display.video_mode_information, ntddvdeo/PVIDEO_MODE_INFORMATION, ntddvdeo/VIDEO_MODE_INFORMATION"
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
-	ntddvdeo.h
api_name:
-	VIDEO_MODE_INFORMATION
product: Windows
targetos: Windows
req.typenames: VIDEO_MODE_INFORMATION, *PVIDEO_MODE_INFORMATION
---

# _VIDEO_MODE_INFORMATION structure


## -description


The VIDEO_MODE_INFORMATION structure contains all of the information about one mode of a video adapter.


## -syntax


````
typedef struct _VIDEO_MODE_INFORMATION {
  ULONG Length;
  ULONG ModeIndex;
  ULONG VisScreenWidth;
  ULONG VisScreenHeight;
  ULONG ScreenStride;
  ULONG NumberOfPlanes;
  ULONG BitsPerPlane;
  ULONG Frequency;
  ULONG XMillimeter;
  ULONG YMillimeter;
  ULONG NumberRedBits;
  ULONG NumberGreenBits;
  ULONG NumberBlueBits;
  ULONG RedMask;
  ULONG GreenMask;
  ULONG BlueMask;
  ULONG AttributeFlags;
  ULONG VideoMemoryBitmapWidth;
  ULONG VideoMemoryBitmapHeight;
  ULONG DriverSpecificAttributeFlags;
} VIDEO_MODE_INFORMATION, *PVIDEO_MODE_INFORMATION;
````


## -struct-fields




### -field Length

Specifies the length, in bytes, of this structure. A miniport driver can use this value to determine the version of this structure. 


### -field ModeIndex

Specifies the index of the particular mode to be used in a call to the miniport driver.


### -field VisScreenWidth

Specifies the number of visible pixels on one horizontal scan line.


### -field VisScreenHeight

Specifies the number of visible lines (or scan lines) on the screen.


### -field ScreenStride

Specifies the number of bytes between the start of one scan line and the next.


### -field NumberOfPlanes

Specifies the number of separate planes combined by the device.


### -field BitsPerPlane

Specifies the number of bits per pixel per plane.


### -field Frequency

Specifies the screen refresh rate, in Hertz.


### -field XMillimeter

Specifies the width, in millimeters, of the active region on the output device.


### -field YMillimeter

Specifies the height, in millimeters, of the active region on the output device.


### -field NumberRedBits

Specifies the number of bits in the red DAC.


### -field NumberGreenBits

Specifies the number of bits in the green DAC.


### -field NumberBlueBits

Specifies the number of bits in the blue DAC.


### -field RedMask

Is the red color mask for a device with direct color modes. For example, to indicate that bits 0 through 4 are to be used for red, use the value 0x001F.


### -field GreenMask

Is the green color mask for a device with direct color modes. For example, to indicate that bits 5 through 9 are to be used for green, use the value 0x03E0.


### -field BlueMask

Is the blue color mask for a device with direct color modes. For example, to indicate that bits 10 through 14 are to be used for blue, use the value 0x7C00.


### -field AttributeFlags

Is a set of flags indicating certain behavior for the device. The flags and their meanings are shown in the following table.

<table>
<tr>
<th>Flag Name</th>
<th>Flag Value</th>
<th>Bit Number</th>
<th>Bit Value and Meaning</th>
</tr>
<tr>
<td>
VIDEO_MODE_COLOR

</td>
<td>
0x0001

</td>
<td>
0

</td>
<td>

<dl>
<dt>0 = Mono-compatible</dt>
<dt>1 = Color</dt>
</dl>


</td>
</tr>
<tr>
<td>
VIDEO_MODE_GRAPHICS

</td>
<td>
0x0002

</td>
<td>
1

</td>
<td>

<dl>
<dt>0 = Text mode</dt>
<dt>1 = Graphics</dt>
</dl>


</td>
</tr>
<tr>
<td>
VIDEO_MODE_PALETTE_DRIVEN

</td>
<td>
0x0004

</td>
<td>
2

</td>
<td>

<dl>
<dt>0 = Colors are direct</dt>
<dt>1 = Colors are indexed to a <a href="https://msdn.microsoft.com/139a10e9-203b-499b-9291-8537eae9189c">palette</a></dt>
</dl>


</td>
</tr>
<tr>
<td>
VIDEO_MODE_MANAGED_PALETTE

</td>
<td>
0x0008

</td>
<td>
3

</td>
<td>

<dl>
<dt>0 = Palette is fixed (must be queried from miniport driver)</dt>
<dt>1 = Palette is settable</dt>
</dl>


</td>
</tr>
<tr>
<td>
VIDEO_MODE_INTERLACED

</td>
<td>
0x0010

</td>
<td>
4

</td>
<td>

<dl>
<dt>0 = Non-interlaced mode</dt>
<dt>1 = Interlaced mode</dt>
</dl>


</td>
</tr>
<tr>
<td>
VIDEO_MODE_NO_OFF_SCREEN

</td>
<td>
0x0020

</td>
<td>
5

</td>
<td>

<dl>
<dt>0 = Offscreen memory is available</dt>
<dt>1 = Offscreen memory cannot be used to store information</dt>
</dl>


</td>
</tr>
<tr>
<td>
VIDEO_MODE_NO_64_BIT_ACCESS

</td>
<td>
0x0040

</td>
<td>
6

</td>
<td>

<dl>
<dt>0 = 64-bit memory writes to <a href="https://msdn.microsoft.com/f697e0db-1db0-4a81-94d8-0ca079885480">frame buffer</a> are handled properly</dt>
<dt>1 = 64-bit memory writes to frame buffer are not handled</dt>
</dl>


</td>
</tr>
</table>
 


### -field VideoMemoryBitmapWidth

Specifies the width, in pixels, of the video memory bitmap. 


### -field VideoMemoryBitmapHeight

Specifies the height, in pixels, of the video memory bitmap.


### -field DriverSpecificAttributeFlags

Is a set of flags indicating certain behavior for the device. These private flags are defined in the miniport driver, and are for the use by the miniport and display drivers only.


## -remarks



The video miniport driver returns an array of VIDEO_MODE_INFORMATION structures in response to an <a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_query_avail_modes.md">IOCTL_VIDEO_QUERY_AVAIL_MODES</a> request, with each structure containing information about one mode of the adapter. The miniport driver returns one VIDEO_MODE_INFORMATION structure that contains information about the adapter's current mode in response to an <a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_query_current_mode.md">IOCTL_VIDEO_QUERY_CURRENT_MODE</a> request.


<dl>
<dt>Three members of VIDEO_MODE_INFORMATION, <b>VisScreenWidth</b>, <b>VideoMemoryBitmapWidth</b>, and <b>ScreenStride</b>, are associated with horizontal screen width. For displays that use one or more bytes per pixel, these members satisfy the inequality </dt>
<dt><b>VisScreenWidth</b> &lt;= <b>VideoMemoryBitmapWidth</b> &lt;= <b>ScreenStride</b>.</dt>
</dl>



<dl>
<dt>In a similar relationship for vertical screen height, <b>VisScreenHeight</b> and <b>VideoMemoryBitmapHeight</b> satisfy the inequality</dt>
<dt><b>VisScreenHeight</b> &lt;= <b>VideoMemoryBitmapHeight</b>.</dt>
</dl>





## -see-also

<a href="..\ntddvdeo\ns-ntddvdeo-_video_memory_information.md">VIDEO_MEMORY_INFORMATION</a>



<a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_query_avail_modes.md">IOCTL_VIDEO_QUERY_AVAIL_MODES</a>



<a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_query_current_mode.md">IOCTL_VIDEO_QUERY_CURRENT_MODE</a>



 

 


