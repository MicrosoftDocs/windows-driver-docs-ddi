---
UID: NI:ntddvdeo.IOCTL_VIDEO_SET_CURSOR_POSITION
title: IOCTL_VIDEO_SET_CURSOR_POSITION
author: windows-driver-content
description: Sets the cursor position (row and column). Miniport drivers for VGA-compatible adapters are required to support this request, which is modal. It is optional for other miniport drivers.
old-location: display\ioctl_video_set_cursor_position.htm
old-project: display
ms.assetid: 80346b99-49f5-4cbf-b524-1c5f40cf441f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_VIDEO_SET_CURSOR_POSITION, IOCTL_VIDEO_SET_CURSOR_POSITION control code [Display Devices], Video_IOCTLs_f95d8cf3-a53e-4b67-867e-7af83e3b0d40.xml, display.ioctl_video_set_cursor_position, ntddvdeo/IOCTL_VIDEO_SET_CURSOR_POSITION
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
-	IOCTL_VIDEO_SET_CURSOR_POSITION
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_SET_CURSOR_POSITION IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



Sets the cursor position (row and column). Miniport drivers for VGA-compatible adapters are required to support this request, which is modal. It is optional for other miniport drivers.




## -ioctlparameters




### -input-buffer

The VRP <b>InputBuffer</b> contains the VIDEO_CURSOR_POSITION structure to be set.


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

