---
UID: NI:ntddvdeo.IOCTL_VIDEO_SAVE_HARDWARE_STATE
title: IOCTL_VIDEO_SAVE_HARDWARE_STATE (ntddvdeo.h)
description: Saves the state of the video adapter in the VRP OutputBuffer. Miniport drivers for VGA-compatible adapters are required to support this nonmodal request; optional for other miniport drivers.
old-location: display\ioctl_video_save_hardware_state.htm
tech.root: display
ms.assetid: 24d786df-2cdd-465c-b468-212e109d5ae1
ms.date: 05/10/2018
ms.keywords: IOCTL_VIDEO_SAVE_HARDWARE_STATE, IOCTL_VIDEO_SAVE_HARDWARE_STATE control, IOCTL_VIDEO_SAVE_HARDWARE_STATE control code [Display Devices], Video_IOCTLs_2595d8e2-5b1e-47dd-b3ba-627425f84215.xml, display.ioctl_video_save_hardware_state, ntddvdeo/IOCTL_VIDEO_SAVE_HARDWARE_STATE
f1_keywords:
 - "ntddvdeo/IOCTL_VIDEO_SAVE_HARDWARE_STATE"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddvdeo.h
api_name:
- IOCTL_VIDEO_SAVE_HARDWARE_STATE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_VIDEO_SAVE_HARDWARE_STATE IOCTL


## -description



Saves the state of the video adapter in the VRP <b>OutputBuffer</b>. Miniport drivers for VGA-compatible adapters are required to support this nonmodal request; optional for other miniport drivers.




## -ioctlparameters




### -input-buffer

None


### -input-buffer-length








### -output-buffer

The miniport driver returns a VIDEO_HARDWARE_STATE structure in the VRP <b>OutputBuffer</b>.


### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

If the miniport driver successfully saves the adapter state, it sets the <b>Information</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_status_block">STATUS_BLOCK</a> structure to <b>sizeof</b>(VIDEO_HARDWARE_STATE); otherwise, the miniport driver sets this member to zero.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_status_block">STATUS_BLOCK</a>
 

 

