---
UID: NI:ntddvdeo.IOCTL_VIDEO_QUERY_POINTER_POSITION
title: IOCTL_VIDEO_QUERY_POINTER_POSITION
author: windows-driver-content
description: Returns the current position of the pointer. Support for this modal request is optional.
old-location: display\ioctl_video_query_pointer_position.htm
old-project: display
ms.assetid: 0dbca53e-5fe0-4435-9f94-45601fbbf950
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IOCTL_VIDEO_QUERY_POINTER_POSITION, IOCTL_VIDEO_QUERY_POINTER_POSITION control, IOCTL_VIDEO_QUERY_POINTER_POSITION control code [Display Devices], Video_IOCTLs_ebaaecc3-ace3-4252-8f01-d80bb1c2472f.xml, display.ioctl_video_query_pointer_position, ntddvdeo/IOCTL_VIDEO_QUERY_POINTER_POSITION
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
-	IOCTL_VIDEO_QUERY_POINTER_POSITION
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_VIDEO_QUERY_POINTER_POSITION IOCTL


## -description



Returns the current position of the pointer. Support for this modal request is optional.




## -ioctlparameters




### -input-buffer

None


### -input-buffer-length








### -output-buffer

The miniport driver returns a VIDEO_POINTER_POSITION structure in the VRP <b>OutputBuffer</b>.


### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

If the miniport driver successfully returns the pointer position, it sets the <b>Information</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff569732">STATUS_BLOCK</a> structure to <b>sizeof</b>(VIDEO_POINTER_POSITION); otherwise, the miniport driver sets this member to zero.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff569732">STATUS_BLOCK</a>
 

 

