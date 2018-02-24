---
UID: NI:ntddvdeo.IOCTL_VIDEO_SET_CURSOR_ATTR
title: IOCTL_VIDEO_SET_CURSOR_ATTR
author: windows-driver-content
description: Sets the cursor size, position, and visibility. Miniport drivers for VGA-compatible adapters are required to support this request, which is modal. Support is optional for other miniport drivers.
old-location: display\ioctl_video_set_cursor_attr.htm
old-project: display
ms.assetid: bb1f426e-6a3d-4644-ad3d-26e5a70b534d
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.ioctl_video_set_cursor_attr, IOCTL_VIDEO_SET_CURSOR_ATTR control code [Display Devices], IOCTL_VIDEO_SET_CURSOR_ATTR, ntddvdeo/IOCTL_VIDEO_SET_CURSOR_ATTR, Video_IOCTLs_7f8f1646-ff57-47fd-afb7-f7ad7e953188.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddvdeo.h
apiname:
-	IOCTL_VIDEO_SET_CURSOR_ATTR
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_SET_CURSOR_ATTR IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



Sets the cursor size, position, and visibility. Miniport drivers for VGA-compatible adapters are required to support this request, which is modal. Support is optional for other miniport drivers.




## -ioctlparameters




### -input-buffer

The VRP <b>InputBuffer</b> contains the VIDEO_CURSOR_ATTRIBUTES structure to be set.


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

