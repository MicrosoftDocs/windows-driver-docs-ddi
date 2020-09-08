---
UID: NI:ntddvdeo.IOCTL_VIDEO_RESTORE_HARDWARE_STATE
title: IOCTL_VIDEO_RESTORE_HARDWARE_STATE (ntddvdeo.h)
description: Restores all values used to set the hardware registers. Miniport drivers for VGA-compatible adapters are required to support this nonmodal request; optional for other miniport drivers.
old-location: display\ioctl_video_restore_hardware_state.htm
tech.root: display
ms.assetid: 94ea36b6-3390-4e67-982d-ee6c2500c0de
ms.date: 05/10/2018
keywords: ["IOCTL_VIDEO_RESTORE_HARDWARE_STATE IOCTL"]
ms.keywords: IOCTL_VIDEO_RESTORE_HARDWARE_STATE, IOCTL_VIDEO_RESTORE_HARDWARE_STATE control, IOCTL_VIDEO_RESTORE_HARDWARE_STATE control code [Display Devices], Video_IOCTLs_2660d342-9c6b-461e-80f9-0c31763689ff.xml, display.ioctl_video_restore_hardware_state, ntddvdeo/IOCTL_VIDEO_RESTORE_HARDWARE_STATE
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_VIDEO_RESTORE_HARDWARE_STATE
 - ntddvdeo/IOCTL_VIDEO_RESTORE_HARDWARE_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddvdeo.h
api_name:
 - IOCTL_VIDEO_RESTORE_HARDWARE_STATE
---

# IOCTL_VIDEO_RESTORE_HARDWARE_STATE IOCTL


## -description

Restores all values used to set the hardware registers. Miniport drivers for VGA-compatible adapters are required to support this nonmodal request; optional for other miniport drivers.

## -ioctlparameters

### -input-buffer

The VRP <b>InputBuffer</b> contains the previously-saved VIDEO_HARDWARE_STATE structure.

### -input-buffer-length

### -output-buffer

None

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

The miniport driver does not set the <b>Information</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_status_block">STATUS_BLOCK</a> structure.

