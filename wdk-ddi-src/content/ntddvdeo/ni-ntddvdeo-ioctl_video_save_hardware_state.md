---
UID: NI:ntddvdeo.IOCTL_VIDEO_SAVE_HARDWARE_STATE
title: IOCTL_VIDEO_SAVE_HARDWARE_STATE
author: windows-driver-content
description: Saves the state of the video adapter in the VRP OutputBuffer. Miniport drivers for VGA-compatible adapters are required to support this nonmodal request; optional for other miniport drivers.
old-location: display\ioctl_video_save_hardware_state.htm
old-project: display
ms.assetid: 24d786df-2cdd-465c-b468-212e109d5ae1
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_VIDEO_SAVE_HARDWARE_STATE, IOCTL_VIDEO_SAVE_HARDWARE_STATE control code [Display Devices], Video_IOCTLs_2595d8e2-5b1e-47dd-b3ba-627425f84215.xml, display.ioctl_video_save_hardware_state, ntddvdeo/IOCTL_VIDEO_SAVE_HARDWARE_STATE
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
-	IOCTL_VIDEO_SAVE_HARDWARE_STATE
product:
- Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_SAVE_HARDWARE_STATE IOCTL


## -description



Saves the state of the video adapter in the VRP <b>OutputBuffer</b>. Miniport drivers for VGA-compatible adapters are required to support this nonmodal request; optional for other miniport drivers.




## -ioctlparameters




### -input-buffer

None


### -input-buffer-length



<text></text>




### -output-buffer

The miniport driver returns a VIDEO_HARDWARE_STATE structure in the VRP <b>OutputBuffer</b>.


### -output-buffer-length



<text></text>




### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

If the miniport driver successfully saves the adapter state, it sets the <b>Information</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff569732">STATUS_BLOCK</a> structure to <b>sizeof</b>(VIDEO_HARDWARE_STATE); otherwise, the miniport driver sets this member to zero.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff569732">STATUS_BLOCK</a>
 

 

