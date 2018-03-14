---
UID: NI:ntddvdeo.IOCTL_VIDEO_RESTORE_HARDWARE_STATE
title: IOCTL_VIDEO_RESTORE_HARDWARE_STATE
author: windows-driver-content
description: Restores all values used to set the hardware registers. Miniport drivers for VGA-compatible adapters are required to support this nonmodal request; optional for other miniport drivers.
old-location: display\ioctl_video_restore_hardware_state.htm
old-project: display
ms.assetid: 94ea36b6-3390-4e67-982d-ee6c2500c0de
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_VIDEO_RESTORE_HARDWARE_STATE, IOCTL_VIDEO_RESTORE_HARDWARE_STATE control code [Display Devices], Video_IOCTLs_2660d342-9c6b-461e-80f9-0c31763689ff.xml, display.ioctl_video_restore_hardware_state, ntddvdeo/IOCTL_VIDEO_RESTORE_HARDWARE_STATE
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
-	IOCTL_VIDEO_RESTORE_HARDWARE_STATE
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_RESTORE_HARDWARE_STATE IOCTL


## -description



Restores all values used to set the hardware registers. Miniport drivers for VGA-compatible adapters are required to support this nonmodal request; optional for other miniport drivers.




## -ioctlparameters




### -input-buffer

The VRP <b>InputBuffer</b> contains the previously-saved VIDEO_HARDWARE_STATE structure.


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

