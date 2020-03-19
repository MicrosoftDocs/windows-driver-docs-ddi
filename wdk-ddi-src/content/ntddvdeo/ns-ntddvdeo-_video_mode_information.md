---
UID: NS:ntddvdeo._VIDEO_MODE_INFORMATION
title: _VIDEO_MODE_INFORMATION (ntddvdeo.h)
description: The VIDEO_MODE_INFORMATION structure contains all of the information about one mode of a video adapter.
old-location: display\video_mode_information.htm
tech.root: display
ms.assetid: aac658d9-b90a-4724-9dc4-af3a561f64bd
ms.date: 05/10/2018
keywords: ["_VIDEO_MODE_INFORMATION structure"]
ms.keywords: "*PVIDEO_MODE_INFORMATION, PVIDEO_MODE_INFORMATION, PVIDEO_MODE_INFORMATION structure pointer [Display Devices], VIDEO_MODE_INFORMATION, VIDEO_MODE_INFORMATION structure [Display Devices], Video_Structs_76f182b8-be55-42d0-948f-29e05e956895.xml, _VIDEO_MODE_INFORMATION, display.video_mode_information, ntddvdeo/PVIDEO_MODE_INFORMATION, ntddvdeo/VIDEO_MODE_INFORMATION"
f1_keywords:
 - "ntddvdeo/VIDEO_MODE_INFORMATION"
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
- VIDEO_MODE_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: VIDEO_MODE_INFORMATION, *PVIDEO_MODE_INFORMATION
---

# _VIDEO_MODE_INFORMATION structure


## -description


The VIDEO_MODE_INFORMATION structure contains all of the information about one mode of a video adapter.


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

| **Flag Name** | **Flag Value** | **Bit Number** | **Bit Value and Meaning** | 
|:--|:--|:--|:--|
| VIDEO_MODE_COLOR | 0x0001 | 0 | 0 = Mono-compatible<br/>1 = Color | 
| VIDEO_MODE_GRAPHICS | 0x0002 | 1 | 0 = Text mode<br/>1 = Graphics | 
| VIDEO_MODE_PALETTE_DRIVEN | 0x0004 | 2 | 0 = Colors are direct<br/>1 = Colors are indexed to a [palette](https://docs.microsoft.com/windows-hardware/drivers/)  | 
| VIDEO_MODE_MANAGED_PALETTE | 0x0008 | 3 | 0 = Palette is fixed (must be queried from miniport driver)<br/>1 = Palette is settable | 
| VIDEO_MODE_INTERLACED | 0x0010 | 4 | 0 = Non-interlaced mode<br/>1 = Interlaced mode | 
| VIDEO_MODE_NO_OFF_SCREEN | 0x0020 | 5 | 0 = Offscreen memory is available<br/>1 = Offscreen memory cannot be used to store information | 
| VIDEO_MODE_NO_64_BIT_ACCESS | 0x0040 | 6 | 0 = 64-bit memory writes to [frame buffer](https://docs.microsoft.com/windows-hardware/drivers/) are handled properly<br/>1 = 64-bit memory writes to frame buffer are not handled |

### -field VideoMemoryBitmapWidth

Specifies the width, in pixels, of the video memory bitmap. 


### -field VideoMemoryBitmapHeight

Specifies the height, in pixels, of the video memory bitmap.


### -field DriverSpecificAttributeFlags

Is a set of flags indicating certain behavior for the device. These private flags are defined in the miniport driver, and are for the use by the miniport and display drivers only.


## -remarks



The video miniport driver returns an array of VIDEO_MODE_INFORMATION structures in response to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvdeo/ni-ntddvdeo-ioctl_video_query_avail_modes">IOCTL_VIDEO_QUERY_AVAIL_MODES</a> request, with each structure containing information about one mode of the adapter. The miniport driver returns one VIDEO_MODE_INFORMATION structure that contains information about the adapter's current mode in response to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvdeo/ni-ntddvdeo-ioctl_video_query_current_mode">IOCTL_VIDEO_QUERY_CURRENT_MODE</a> request.


<dl>
<dt>Three members of VIDEO_MODE_INFORMATION, <b>VisScreenWidth</b>, <b>VideoMemoryBitmapWidth</b>, and <b>ScreenStride</b>, are associated with horizontal screen width. For displays that use one or more bytes per pixel, these members satisfy the inequality </dt>
<dt><b>VisScreenWidth</b> <= <b>VideoMemoryBitmapWidth</b> <= <b>ScreenStride</b>.</dt>
</dl>



<dl>
<dt>In a similar relationship for vertical screen height, <b>VisScreenHeight</b> and <b>VideoMemoryBitmapHeight</b> satisfy the inequality</dt>
<dt><b>VisScreenHeight</b> <= <b>VideoMemoryBitmapHeight</b>.</dt>
</dl>





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvdeo/ni-ntddvdeo-ioctl_video_query_avail_modes">IOCTL_VIDEO_QUERY_AVAIL_MODES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvdeo/ni-ntddvdeo-ioctl_video_query_current_mode">IOCTL_VIDEO_QUERY_CURRENT_MODE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvdeo/ns-ntddvdeo-_video_memory_information">VIDEO_MEMORY_INFORMATION</a>
 

 

