---
UID: NI:ntddvdeo.IOCTL_VIDEO_ENABLE_CURSOR
title: IOCTL_VIDEO_ENABLE_CURSOR (ntddvdeo.h)
description: Makes the cursor visible by enabling the cursor's visibility attribute. Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers.
old-location: display\ioctl_video_enable_cursor.htm
tech.root: display
ms.assetid: 727add49-3224-4bc0-8d98-971e282c575a
ms.date: 05/10/2018
ms.keywords: IOCTL_VIDEO_ENABLE_CURSOR, IOCTL_VIDEO_ENABLE_CURSOR control, IOCTL_VIDEO_ENABLE_CURSOR control code [Display Devices], Video_IOCTLs_adcda61e-67fe-4c4e-a6df-015ff1d95c36.xml, display.ioctl_video_enable_cursor, ntddvdeo/IOCTL_VIDEO_ENABLE_CURSOR
f1_keywords:
 - "ntddvdeo/IOCTL_VIDEO_ENABLE_CURSOR"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddvdeo.h
api_name:
- IOCTL_VIDEO_ENABLE_CURSOR
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_VIDEO_ENABLE_CURSOR IOCTL


## -description



Makes the cursor visible by enabling the cursor's visibility attribute. Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers.




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

