---
UID: NI:ntddvdeo.IOCTL_VIDEO_SET_COLOR_REGISTERS
title: IOCTL_VIDEO_SET_COLOR_REGISTERS
author: windows-driver-content
description: Sets the adapter's color registers to the specified RGB values. If the adapter has a color look up table (CLUT), sometimes called a palette, the miniport driver is required to support this modal request.
old-location: display\ioctl_video_set_color_registers.htm
old-project: display
ms.assetid: efaea94e-0cfd-49a7-b8dc-452aa006b024
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_VIDEO_SET_COLOR_REGISTERS, IOCTL_VIDEO_SET_COLOR_REGISTERS control code [Display Devices], Video_IOCTLs_29dd4eb9-3c05-4b2f-8572-66b7c599fef1.xml, display.ioctl_video_set_color_registers, ntddvdeo/IOCTL_VIDEO_SET_COLOR_REGISTERS
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
-	IOCTL_VIDEO_SET_COLOR_REGISTERS
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_SET_COLOR_REGISTERS IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



Sets the adapter's color registers to the specified RGB values. If the adapter has a color look up table (CLUT), sometimes called a palette, the miniport driver is required to support this modal request.




## -ioctlparameters




### -input-buffer

The VRP <b>InputBuffer</b> contains a VIDEO_CLUT structure, specifying an array of RGB values to be set.


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

