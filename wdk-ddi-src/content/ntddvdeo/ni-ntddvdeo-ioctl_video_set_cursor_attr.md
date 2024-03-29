---
UID: NI:ntddvdeo.IOCTL_VIDEO_SET_CURSOR_ATTR
title: IOCTL_VIDEO_SET_CURSOR_ATTR (ntddvdeo.h)
description: Sets the cursor size, position, and visibility. Miniport drivers for VGA-compatible adapters are required to support this request, which is modal. Support is optional for other miniport drivers.
old-location: display\ioctl_video_set_cursor_attr.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["IOCTL_VIDEO_SET_CURSOR_ATTR IOCTL"]
ms.keywords: IOCTL_VIDEO_SET_CURSOR_ATTR, IOCTL_VIDEO_SET_CURSOR_ATTR control, IOCTL_VIDEO_SET_CURSOR_ATTR control code [Display Devices], Video_IOCTLs_7f8f1646-ff57-47fd-afb7-f7ad7e953188.xml, display.ioctl_video_set_cursor_attr, ntddvdeo/IOCTL_VIDEO_SET_CURSOR_ATTR
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
 - IOCTL_VIDEO_SET_CURSOR_ATTR
 - ntddvdeo/IOCTL_VIDEO_SET_CURSOR_ATTR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddvdeo.h
api_name:
 - IOCTL_VIDEO_SET_CURSOR_ATTR
---

# IOCTL_VIDEO_SET_CURSOR_ATTR IOCTL


## -description

Sets the cursor size, position, and visibility. Miniport drivers for VGA-compatible adapters are required to support this request, which is modal. Support is optional for other miniport drivers.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

The VRP <b>InputBuffer</b> contains the VIDEO_CURSOR_ATTRIBUTES structure to be set.

### -input-buffer-length

### -output-buffer

None

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

The miniport driver does not set the <b>Information</b> member of the <a href="/windows-hardware/drivers/ddi/video/ns-video-_status_block">STATUS_BLOCK</a> structure.
