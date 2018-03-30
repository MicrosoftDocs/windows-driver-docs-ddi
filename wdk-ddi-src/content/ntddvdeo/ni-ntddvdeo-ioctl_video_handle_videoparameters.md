---
UID: NI:ntddvdeo.IOCTL_VIDEO_HANDLE_VIDEOPARAMETERS
title: IOCTL_VIDEO_HANDLE_VIDEOPARAMETERS
author: windows-driver-content
description: Gets the capabilities of the device's television connector and/or copy protection hardware, or sets the desired functionality on the copy protection hardware.
old-location: display\ioctl_video_handle_videoparameters.htm
old-project: display
ms.assetid: 5c48d2b7-3dcc-4025-ab3c-12085369cd7d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_VIDEO_HANDLE_VIDEOPARAMETERS, IOCTL_VIDEO_HANDLE_VIDEOPARAMETERS control code [Display Devices], Video_IOCTLs_c94e510e-22f7-47af-8e82-f84ef2b926c6.xml, display.ioctl_video_handle_videoparameters, ntddvdeo/IOCTL_VIDEO_HANDLE_VIDEOPARAMETERS
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
-	IOCTL_VIDEO_HANDLE_VIDEOPARAMETERS
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_HANDLE_VIDEOPARAMETERS IOCTL


## -description



Gets the capabilities of the device's television connector and/or copy protection hardware, or sets the desired functionality on the copy protection hardware. Adapters that support TV connectors should provide support for this modal IOCTL. See <a href="https://msdn.microsoft.com/7d7d44b5-3248-4bee-bc4d-e02fd3c606a7">TV Connector and Copy Protection Support in Video Miniport Drivers</a> for details.




## -ioctlparameters




### -input-buffer

The VRP <b>InputBuffer</b> contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570173">VIDEOPARAMETERS</a> structure that describes the action to be performed by the miniport driver.


### -input-buffer-length



<text></text>




### -output-buffer

The miniport driver returns the VIDEOPARAMETERS structure in the VRP <b>OutputBuffer</b>.


### -output-buffer-length



<text></text>




### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

If the miniport driver successfully gets or sets the requested information, it sets the <b>Information</b> member of the VRP's <a href="https://msdn.microsoft.com/library/windows/hardware/ff569732">STATUS_BLOCK</a> to <b>sizeof</b>(VIDEOPARAMETERS); otherwise, the miniport driver sets this member to zero.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff569732">STATUS_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570173">VIDEOPARAMETERS</a>
 

 

