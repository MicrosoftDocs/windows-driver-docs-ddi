---
UID: NI:ntddvdeo.IOCTL_VIDEO_SET_CURRENT_MODE
title: IOCTL_VIDEO_SET_CURRENT_MODE (ntddvdeo.h)
description: Sets the adapter to the specified operating mode.
old-location: display\ioctl_video_set_current_mode.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["IOCTL_VIDEO_SET_CURRENT_MODE IOCTL"]
ms.keywords: IOCTL_VIDEO_SET_CURRENT_MODE, IOCTL_VIDEO_SET_CURRENT_MODE control, IOCTL_VIDEO_SET_CURRENT_MODE control code [Display Devices], Video_IOCTLs_df8e3e45-0a72-427b-b47f-49bc936d53a5.xml, display.ioctl_video_set_current_mode, ntddvdeo/IOCTL_VIDEO_SET_CURRENT_MODE
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
 - IOCTL_VIDEO_SET_CURRENT_MODE
 - ntddvdeo/IOCTL_VIDEO_SET_CURRENT_MODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddvdeo.h
api_name:
 - IOCTL_VIDEO_SET_CURRENT_MODE
---

# IOCTL_VIDEO_SET_CURRENT_MODE IOCTL


## -description

Sets the adapter to the specified operating mode. Miniport drivers are required to support this nonmodal request because it resets the current mode. The miniport driver must also consider the two high order flags which are used to additionally control the mode set operation. See <a href="/windows-hardware/drivers/ddi/ntddvdeo/ns-ntddvdeo-_video_mode">VIDEO_MODE</a> for further information.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

The VRP <b>InputBuffer</b> contains a <a href="/windows-hardware/drivers/ddi/ntddvdeo/ns-ntddvdeo-_video_mode">VIDEO_MODE</a> structure specifying the mode to be set.

### -input-buffer-length

### -output-buffer

None

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

The miniport driver does not set the <b>Information</b> member of the <a href="/windows-hardware/drivers/ddi/video/ns-video-_status_block">STATUS_BLOCK</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddvdeo/ns-ntddvdeo-_video_mode">VIDEO_MODE</a>
