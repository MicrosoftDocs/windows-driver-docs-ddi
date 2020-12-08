---
UID: NI:ntddvdeo.IOCTL_VIDEO_ENABLE_POINTER
title: IOCTL_VIDEO_ENABLE_POINTER (ntddvdeo.h)
description: Makes the pointer visible by enabling pointer attributes. Support for this modal request is optional; however, if a miniport driver supports this request, it must process an IOCTL_VIDEO_SET_POINTER_ATTR request before processing this request.
old-location: display\ioctl_video_enable_pointer.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["IOCTL_VIDEO_ENABLE_POINTER IOCTL"]
ms.keywords: IOCTL_VIDEO_ENABLE_POINTER, IOCTL_VIDEO_ENABLE_POINTER control, IOCTL_VIDEO_ENABLE_POINTER control code [Display Devices], Video_IOCTLs_89a9a8cc-bfd6-4969-bb8f-26d72cbaa807.xml, display.ioctl_video_enable_pointer, ntddvdeo/IOCTL_VIDEO_ENABLE_POINTER
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
 - IOCTL_VIDEO_ENABLE_POINTER
 - ntddvdeo/IOCTL_VIDEO_ENABLE_POINTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddvdeo.h
api_name:
 - IOCTL_VIDEO_ENABLE_POINTER
---

# IOCTL_VIDEO_ENABLE_POINTER IOCTL


## -description

Makes the pointer visible by enabling pointer attributes. Support for this modal request is optional; however, if a miniport driver supports this request, it must process an <a href="/windows-hardware/drivers/ddi/ntddvdeo/ni-ntddvdeo-ioctl_video_set_pointer_attr">IOCTL_VIDEO_SET_POINTER_ATTR</a> request before processing this request.

## -ioctlparameters

### -input-buffer

None

### -input-buffer-length

### -output-buffer

None

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

The miniport driver does not set the <b>Information</b> member of the <a href="/windows-hardware/drivers/ddi/video/ns-video-_status_block">STATUS_BLOCK</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddvdeo/ni-ntddvdeo-ioctl_video_set_pointer_attr">IOCTL_VIDEO_SET_POINTER_ATTR</a>
