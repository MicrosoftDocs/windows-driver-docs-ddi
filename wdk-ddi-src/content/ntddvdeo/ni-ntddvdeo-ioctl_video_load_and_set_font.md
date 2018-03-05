---
UID: NI:ntddvdeo.IOCTL_VIDEO_LOAD_AND_SET_FONT
title: IOCTL_VIDEO_LOAD_AND_SET_FONT
author: windows-driver-content
description: Loads a user-defined font on the adapter. Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers.
old-location: display\ioctl_video_load_and_set_font.htm
old-project: display
ms.assetid: 13771df5-f66c-4dd9-b2d3-4477fda82f8f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_VIDEO_LOAD_AND_SET_FONT, IOCTL_VIDEO_LOAD_AND_SET_FONT control code [Display Devices], Video_IOCTLs_f68527dd-7070-4a47-91e2-9e64610508b7.xml, display.ioctl_video_load_and_set_font, ntddvdeo/IOCTL_VIDEO_LOAD_AND_SET_FONT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddvdeo.h
req.include-header: 
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
-	IOCTL_VIDEO_LOAD_AND_SET_FONT
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_LOAD_AND_SET_FONT IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



Loads a user-defined font on the adapter. Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers.




## -ioctlparameters




### -input-buffer

The VRP <b>InputBuffer</b> contains a VIDEO_LOAD_FONT_INFORMATION structure describing the font's width, height, and size, as well as a pointer to the font buffer.


### -input-buffer-length



<text></text>




### -output-buffer

None


### -output-buffer-length



<text></text>




### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The miniport driver does not set the <b>Information</b> member of the <a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a> structure.

