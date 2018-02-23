---
UID: NI:ntddvdeo.IOCTL_VIDEO_DISABLE_CURSOR
title: IOCTL_VIDEO_DISABLE_CURSOR
author: windows-driver-content
description: Makes the cursor invisible by disabling the cursor's visibility attribute. Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers.
old-location: display\ioctl_video_disable_cursor.htm
old-project: display
ms.assetid: bbc3564d-bed5-45fb-9ee3-ed98073b6eba
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: display.ioctl_video_disable_cursor, IOCTL_VIDEO_DISABLE_CURSOR control code [Display Devices], IOCTL_VIDEO_DISABLE_CURSOR, ntddvdeo/IOCTL_VIDEO_DISABLE_CURSOR, Video_IOCTLs_664ec9f1-497c-4890-b812-9691776b1988.xml
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
-	IOCTL_VIDEO_DISABLE_CURSOR
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_DISABLE_CURSOR IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



Makes the cursor invisible by disabling the cursor's visibility attribute. Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers.




## -ioctlparameters




### -input-buffer

None


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

