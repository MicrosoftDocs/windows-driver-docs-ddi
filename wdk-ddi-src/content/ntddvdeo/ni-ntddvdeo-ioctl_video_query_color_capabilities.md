---
UID: NI:ntddvdeo.IOCTL_VIDEO_QUERY_COLOR_CAPABILITIES
title: IOCTL_VIDEO_QUERY_COLOR_CAPABILITIES (ntddvdeo.h)
description: Returns the color-capabilities information found in the VDDP description file for the adapter.
old-location: display\ioctl_video_query_color_capabilities.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["IOCTL_VIDEO_QUERY_COLOR_CAPABILITIES IOCTL"]
ms.keywords: IOCTL_VIDEO_QUERY_COLOR_CAPABILITIES, IOCTL_VIDEO_QUERY_COLOR_CAPABILITIES control, IOCTL_VIDEO_QUERY_COLOR_CAPABILITIES control code [Display Devices], Video_IOCTLs_26b0d5c4-d7b5-4056-9d78-6b9fa9a8ab72.xml, display.ioctl_video_query_color_capabilities, ntddvdeo/IOCTL_VIDEO_QUERY_COLOR_CAPABILITIES
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
 - IOCTL_VIDEO_QUERY_COLOR_CAPABILITIES
 - ntddvdeo/IOCTL_VIDEO_QUERY_COLOR_CAPABILITIES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddvdeo.h
api_name:
 - IOCTL_VIDEO_QUERY_COLOR_CAPABILITIES
---

# IOCTL_VIDEO_QUERY_COLOR_CAPABILITIES IOCTL


## -description

Returns the color-capabilities information found in the VDDP description file for the adapter. Support for this nonmodal request is optional. However, if a miniport driver supports this request, it cannot return a subset of the color-capabilities information.

## -ioctlparameters

### -ioctl-major-code

### -input-buffer

None

### -input-buffer-length

### -output-buffer

The miniport driver returns all VIDEO_COLOR_CAPABILITIES information in the VRP <b>OutputBuffer</b>.

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

If the miniport driver successfully returns the color-capabilities data, it sets the <b>Information</b> member of the <a href="/windows-hardware/drivers/ddi/video/ns-video-_status_block">STATUS_BLOCK</a> structure to <b>sizeof</b>(VIDEO_COLOR_CAPABILITIES); otherwise, the miniport driver sets this member to zero.

## -see-also

<a href="/windows-hardware/drivers/ddi/video/ns-video-_status_block">STATUS_BLOCK</a>
