---
UID: NI:ntddvdeo.IOCTL_VIDEO_SET_PALETTE_REGISTERS
title: IOCTL_VIDEO_SET_PALETTE_REGISTERS (ntddvdeo.h)
description: Loads a specified portion of the adapter palette registers with an array of colors. Miniport drivers for VGA-compatible adapters are required to support this request, which is modal. Support is optional for other miniport drivers.
old-location: display\ioctl_video_set_palette_registers.htm
tech.root: display
ms.assetid: f36dc8cf-2141-4ee2-9f23-ae996a0f0d97
ms.date: 05/10/2018
keywords: ["IOCTL_VIDEO_SET_PALETTE_REGISTERS IOCTL"]
ms.keywords: IOCTL_VIDEO_SET_PALETTE_REGISTERS, IOCTL_VIDEO_SET_PALETTE_REGISTERS control, IOCTL_VIDEO_SET_PALETTE_REGISTERS control code [Display Devices], Video_IOCTLs_d8a3a22e-037b-4e82-b542-e5a5e4a7fef7.xml, display.ioctl_video_set_palette_registers, ntddvdeo/IOCTL_VIDEO_SET_PALETTE_REGISTERS
f1_keywords:
 - "ntddvdeo/IOCTL_VIDEO_SET_PALETTE_REGISTERS"
 - "IOCTL_VIDEO_SET_PALETTE_REGISTERS"
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
- IOCTL_VIDEO_SET_PALETTE_REGISTERS
targetos: Windows
req.typenames: 
---

# IOCTL_VIDEO_SET_PALETTE_REGISTERS IOCTL


## -description



Loads a specified portion of the adapter palette registers with an array of colors. Miniport drivers for VGA-compatible adapters are required to support this request, which is modal. Support is optional for other miniport drivers.




## -ioctlparameters




### -input-buffer

The VRP <b>InputBuffer</b> contains the VIDEO_PALETTE_DATA structure, specifying an array of colors to be set in the palette registers.


### -input-buffer-length








### -output-buffer

None


### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

The miniport driver does not set the <b>Information</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_status_block">STATUS_BLOCK</a> structure.

