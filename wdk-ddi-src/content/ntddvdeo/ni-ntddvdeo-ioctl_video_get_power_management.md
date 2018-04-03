---
UID: NI:ntddvdeo.IOCTL_VIDEO_GET_POWER_MANAGEMENT
title: IOCTL_VIDEO_GET_POWER_MANAGEMENT
author: windows-driver-content
description: This IOCTL is obsolete in Windows 2000 and later, and is no longer supported.
old-location: display\ioctl_video_get_power_management.htm
old-project: display
ms.assetid: 5d45b65b-39f6-4a8c-ad88-958e3b950cde
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_VIDEO_GET_POWER_MANAGEMENT, IOCTL_VIDEO_GET_POWER_MANAGEMENT control code [Display Devices], Video_IOCTLs_2595a142-7478-47f5-bb45-1651903f53ab.xml, display.ioctl_video_get_power_management, ntddvdeo/IOCTL_VIDEO_GET_POWER_MANAGEMENT
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
-	IOCTL_VIDEO_GET_POWER_MANAGEMENT
product:
- Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_GET_POWER_MANAGEMENT IOCTL


## -description



This IOCTL is <b>obsolete</b> in Windows 2000 and later, and is no longer supported. A Plug and Play video miniport driver should implement the <a href="https://msdn.microsoft.com/747cfbfb-2a38-4a0d-b8c6-662d0c3967ba">HwVidGetPowerState</a> function, which provides similar functionality.

Returns the current power-consumption level of the adapter. Support for this nonmodal IOCTL is required for adapters that conform to the VESA DPMS standard.




## -ioctlparameters




### -input-buffer

None


### -input-buffer-length



<text></text>




### -output-buffer

The miniport driver returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570542">VIDEO_POWER_MANAGEMENT</a> structure in the VRP <b>OutputBuffer</b>.


### -output-buffer-length



<text></text>




### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

If the miniport driver successfully returns the power-consumption information, it sets the <b>Information</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff569732">STATUS_BLOCK</a> structure to <b>sizeof</b>(VIDEO_POWER_MANAGEMENT); otherwise, the miniport driver sets this member to zero.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff569732">STATUS_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570542">VIDEO_POWER_MANAGEMENT</a>
 

 

