---
UID: NF:video.VideoPortGetRomImage
title: VideoPortGetRomImage function (video.h)
description: Reads the device's read-only memory (ROM).
old-location: display\videoportgetromimage.htm
tech.root: display
ms.assetid: e4930661-fb88-458b-9460-129ab057e0f4
ms.date: 05/10/2018
keywords: ["VideoPortGetRomImage function"]
ms.keywords: VideoPortGetRomImage, VideoPortGetRomImage function [Display Devices], VideoPort_Functions_070e50af-a33d-4dc5-9bd1-9f60367f49b2.xml, display.videoportgetromimage, video/VideoPortGetRomImage
f1_keywords:
 - "video/VideoPortGetRomImage"
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Videoprt.sys
api_name:
- VideoPortGetRomImage
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortGetRomImage function


## -description


Reads the device's read-only memory (ROM).


## -parameters




### -param HwDeviceExtension [in]

A pointer to the miniport driver's device extension.


### -param Unused1 [in]

Currently ignored by the video port driver; should be set to <b>NULL</b>.


### -param Unused2 [in]

Currently ignored by the video port driver; should be set to zero.


### -param Length [in]

Either the number of bytes of ROM data that the video port driver should read and return, or zero.


## -returns



<b>VideoPortGetRomImage</b> returns a pointer to a buffer containing the device's ROM (BIOS) data on success; otherwise, returns <b>NULL</b> to indicate either there was insufficient memory for the operation, or the device's ROM could not be accessed.




## -remarks



<b>VideoPortGetRomImage</b> does not read ROM using the legacy 0xC0000 mapping. It reads ROM that can be discovered using the ACPI_METHOD_DISPLAY_ROM method or the ROM base address register.

The ACPI_METHOD_DISPLAY_ROM alias, defined in Dispmprt.h, represents the method used to obtain the BIOS ROM image. This method is required when the ROM image is stored in a proprietary format such as the system BIOS ROM. This method is not necessary if the ROM image can be read through a standard PCI interface.

The video port driver allocates a buffer of <i>Length</i> bytes and fills it with data read from the device's ROM. The video port driver always reads <i>Length</i> bytes from the beginning of the device's ROM.

If a miniport driver calls <b>VideoPortGetRomImage</b> multiple times, the video port driver will free the buffer from a previous call before allocating and returning a buffer in the current call. Consequently, a miniport driver must only reference the pointer returned by this call to <b>VideoPortGetRomImage</b>.

The miniport driver can free the buffer allocated by the video port driver by calling <b>VideoPortGetRomImage</b> with a <i>Length</i> of zero. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportscanrom">VideoPortScanRom</a>
 

 

