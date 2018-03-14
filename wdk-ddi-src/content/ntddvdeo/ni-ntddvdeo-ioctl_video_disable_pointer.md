---
UID: NI:ntddvdeo.IOCTL_VIDEO_DISABLE_POINTER
title: IOCTL_VIDEO_DISABLE_POINTER
author: windows-driver-content
description: Makes the pointer invisible by disabling the pointer attributes. Support for this modal request is optional.
old-location: display\ioctl_video_disable_pointer.htm
old-project: display
ms.assetid: 0ec5597b-53a4-4711-84f0-d307ad96ef9d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_VIDEO_DISABLE_POINTER, IOCTL_VIDEO_DISABLE_POINTER control code [Display Devices], Video_IOCTLs_b988a11c-2f01-48bb-b07e-2da28f729369.xml, display.ioctl_video_disable_pointer, ntddvdeo/IOCTL_VIDEO_DISABLE_POINTER
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
-	IOCTL_VIDEO_DISABLE_POINTER
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_DISABLE_POINTER IOCTL


## -description



Makes the pointer invisible by disabling the pointer attributes. Support for this modal request is optional.




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

