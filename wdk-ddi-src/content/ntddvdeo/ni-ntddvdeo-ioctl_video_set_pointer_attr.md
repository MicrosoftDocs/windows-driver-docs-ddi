---
UID: NI:ntddvdeo.IOCTL_VIDEO_SET_POINTER_ATTR
title: IOCTL_VIDEO_SET_POINTER_ATTR (ntddvdeo.h)
description: Sets the pointer attributes.
old-location: display\ioctl_video_set_pointer_attr.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["IOCTL_VIDEO_SET_POINTER_ATTR IOCTL"]
ms.keywords: IOCTL_VIDEO_SET_POINTER_ATTR, IOCTL_VIDEO_SET_POINTER_ATTR control, IOCTL_VIDEO_SET_POINTER_ATTR control code [Display Devices], Video_IOCTLs_78cd33bc-5c7d-4b6c-bfac-64e0cc33e475.xml, display.ioctl_video_set_pointer_attr, ntddvdeo/IOCTL_VIDEO_SET_POINTER_ATTR
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
 - IOCTL_VIDEO_SET_POINTER_ATTR
 - ntddvdeo/IOCTL_VIDEO_SET_POINTER_ATTR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddvdeo.h
api_name:
 - IOCTL_VIDEO_SET_POINTER_ATTR
---

# IOCTL_VIDEO_SET_POINTER_ATTR IOCTL


## -description

Sets the pointer attributes. Support for this modal request is optional. A supporting miniport driver can fail this request (for example, if the attributes specify a larger pointer than the miniport driver can supply). When a miniport driver fails this request, the corresponding display driver must manage the pointer.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

The VRP <b>InputBuffer</b> contains the VIDEO_POINTER_ATTRIBUTES structure to be set.

### -input-buffer-length

### -output-buffer

None

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

The miniport driver does not set the <b>Information</b> member of the <a href="/windows-hardware/drivers/ddi/video/ns-video-_status_block">STATUS_BLOCK</a> structure.
