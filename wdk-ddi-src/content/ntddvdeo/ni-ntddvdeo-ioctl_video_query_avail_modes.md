---
UID: NI:ntddvdeo.IOCTL_VIDEO_QUERY_AVAIL_MODES
title: IOCTL_VIDEO_QUERY_AVAIL_MODES (ntddvdeo.h)
description: Returns information about each video mode supported by the adapter. Miniport drivers are required to support this nonmodal request.
old-location: display\ioctl_video_query_avail_modes.htm
tech.root: display
ms.assetid: 926ec9d5-090c-490d-a0ea-90cc515bdec7
ms.date: 05/10/2018
keywords: ["IOCTL_VIDEO_QUERY_AVAIL_MODES IOCTL"]
ms.keywords: IOCTL_VIDEO_QUERY_AVAIL_MODES, IOCTL_VIDEO_QUERY_AVAIL_MODES control, IOCTL_VIDEO_QUERY_AVAIL_MODES control code [Display Devices], Video_IOCTLs_a846ef88-234e-4867-a3fe-4d8c9b43e00e.xml, display.ioctl_video_query_avail_modes, ntddvdeo/IOCTL_VIDEO_QUERY_AVAIL_MODES
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
 - IOCTL_VIDEO_QUERY_AVAIL_MODES
 - ntddvdeo/IOCTL_VIDEO_QUERY_AVAIL_MODES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddvdeo.h
api_name:
 - IOCTL_VIDEO_QUERY_AVAIL_MODES
---

# IOCTL_VIDEO_QUERY_AVAIL_MODES IOCTL


## -description

Returns information about each video mode supported by the adapter. Miniport drivers are required to support this nonmodal request.

## -ioctlparameters

### -input-buffer

None

### -input-buffer-length

### -output-buffer

The miniport driver returns an array of <a href="/windows-hardware/drivers/ddi/ntddvdeo/ns-ntddvdeo-_video_mode_information">VIDEO_MODE_INFORMATION</a> structures in the VRP <b>OutputBuffer</b>.

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

If the miniport driver successfully returns the available modes, it sets the <b>Information</b> member of the <a href="/windows-hardware/drivers/ddi/video/ns-video-_status_block">STATUS_BLOCK</a> structure to (<b>sizeof</b>(VIDEO_MODE_INFORMATION) * <i>NumberOfSupportedModes)</i>; otherwise, the miniport driver sets this member to zero.

## -see-also

<a href="/windows-hardware/drivers/ddi/video/ns-video-_status_block">STATUS_BLOCK</a>



<a href="/windows-hardware/drivers/ddi/ntddvdeo/ns-ntddvdeo-_video_mode_information">VIDEO_MODE_INFORMATION</a>