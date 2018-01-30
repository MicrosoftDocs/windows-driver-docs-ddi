---
UID: NI:ntddvdeo.IOCTL_VIDEO_ENABLE_CURSOR
title: IOCTL_VIDEO_ENABLE_CURSOR
author: windows-driver-content
description: Makes the cursor visible by enabling the cursor's visibility attribute. Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers.
old-location: display\ioctl_video_enable_cursor.htm
old-project: display
ms.assetid: 727add49-3224-4bc0-8d98-971e282c575a
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.ioctl_video_enable_cursor, IOCTL_VIDEO_ENABLE_CURSOR control code [Display Devices], IOCTL_VIDEO_ENABLE_CURSOR, ntddvdeo/IOCTL_VIDEO_ENABLE_CURSOR, Video_IOCTLs_adcda61e-67fe-4c4e-a6df-015ff1d95c36.xml
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
-	IOCTL_VIDEO_ENABLE_CURSOR
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_ENABLE_CURSOR IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



Makes the cursor visible by enabling the cursor's visibility attribute. Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers.




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

