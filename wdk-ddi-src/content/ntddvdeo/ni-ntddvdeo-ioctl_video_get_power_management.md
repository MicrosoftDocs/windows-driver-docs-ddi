---
UID: NI:ntddvdeo.IOCTL_VIDEO_GET_POWER_MANAGEMENT
title: IOCTL_VIDEO_GET_POWER_MANAGEMENT (ntddvdeo.h)
description: This IOCTL is obsolete in Windows 2000 and later, and is no longer supported.
old-location: display\ioctl_video_get_power_management.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["IOCTL_VIDEO_GET_POWER_MANAGEMENT IOCTL"]
ms.keywords: IOCTL_VIDEO_GET_POWER_MANAGEMENT, IOCTL_VIDEO_GET_POWER_MANAGEMENT control, IOCTL_VIDEO_GET_POWER_MANAGEMENT control code [Display Devices], Video_IOCTLs_2595a142-7478-47f5-bb45-1651903f53ab.xml, display.ioctl_video_get_power_management, ntddvdeo/IOCTL_VIDEO_GET_POWER_MANAGEMENT
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
 - IOCTL_VIDEO_GET_POWER_MANAGEMENT
 - ntddvdeo/IOCTL_VIDEO_GET_POWER_MANAGEMENT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddvdeo.h
api_name:
 - IOCTL_VIDEO_GET_POWER_MANAGEMENT
---

# IOCTL_VIDEO_GET_POWER_MANAGEMENT IOCTL


## -description

This IOCTL is <b>obsolete</b> in Windows 2000 and later, and is no longer supported. A Plug and Play video miniport driver should implement the <a href="/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_power_get">HwVidGetPowerState</a> function, which provides similar functionality.

Returns the current power-consumption level of the adapter. Support for this nonmodal IOCTL is required for adapters that conform to the VESA DPMS standard.

## -ioctlparameters

### -input-buffer

None

### -input-buffer-length

### -output-buffer

The miniport driver returns a <a href="/windows-hardware/drivers/ddi/ntddvdeo/ns-ntddvdeo-_video_power_management">VIDEO_POWER_MANAGEMENT</a> structure in the VRP <b>OutputBuffer</b>.

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

If the miniport driver successfully returns the power-consumption information, it sets the <b>Information</b> member of the <a href="/windows-hardware/drivers/ddi/video/ns-video-_status_block">STATUS_BLOCK</a> structure to <b>sizeof</b>(VIDEO_POWER_MANAGEMENT); otherwise, the miniport driver sets this member to zero.

## -see-also

<a href="/windows-hardware/drivers/ddi/video/ns-video-_status_block">STATUS_BLOCK</a>



<a href="/windows-hardware/drivers/ddi/ntddvdeo/ns-ntddvdeo-_video_power_management">VIDEO_POWER_MANAGEMENT</a>
