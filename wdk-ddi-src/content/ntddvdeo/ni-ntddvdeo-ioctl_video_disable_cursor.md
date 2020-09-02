---
UID: NI:ntddvdeo.IOCTL_VIDEO_DISABLE_CURSOR
title: IOCTL_VIDEO_DISABLE_CURSOR (ntddvdeo.h)
description: Makes the cursor invisible by disabling the cursor's visibility attribute. Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers.
old-location: display\ioctl_video_disable_cursor.htm
tech.root: display
ms.assetid: bbc3564d-bed5-45fb-9ee3-ed98073b6eba
ms.date: 05/10/2018
keywords: ["IOCTL_VIDEO_DISABLE_CURSOR IOCTL"]
ms.keywords: IOCTL_VIDEO_DISABLE_CURSOR, IOCTL_VIDEO_DISABLE_CURSOR control, IOCTL_VIDEO_DISABLE_CURSOR control code [Display Devices], Video_IOCTLs_664ec9f1-497c-4890-b812-9691776b1988.xml, display.ioctl_video_disable_cursor, ntddvdeo/IOCTL_VIDEO_DISABLE_CURSOR
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
 - IOCTL_VIDEO_DISABLE_CURSOR
 - ntddvdeo/IOCTL_VIDEO_DISABLE_CURSOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddvdeo.h
api_name:
 - IOCTL_VIDEO_DISABLE_CURSOR
---

# IOCTL_VIDEO_DISABLE_CURSOR IOCTL


## -description

Makes the cursor invisible by disabling the cursor's visibility attribute. Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers.

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

The miniport driver does not set the <b>Information</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_status_block">STATUS_BLOCK</a> structure.

