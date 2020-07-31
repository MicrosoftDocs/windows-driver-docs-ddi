---
UID: NI:ntddvdeo.IOCTL_VIDEO_GET_BANK_SELECT_CODE
title: IOCTL_VIDEO_GET_BANK_SELECT_CODE (ntddvdeo.h)
description: Returns a block of x86-specific executable code to be used by a high-resolution SVGA display driver for bank switching. Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers.
old-location: display\ioctl_video_get_bank_select_code.htm
tech.root: display
ms.assetid: 2d5f0224-dbed-461b-bf05-4db7ae7d810e
ms.date: 05/10/2018
keywords: ["IOCTL_VIDEO_GET_BANK_SELECT_CODE IOCTL"]
ms.keywords: IOCTL_VIDEO_GET_BANK_SELECT_CODE, IOCTL_VIDEO_GET_BANK_SELECT_CODE control, IOCTL_VIDEO_GET_BANK_SELECT_CODE control code [Display Devices], Video_IOCTLs_3e7414c6-20b6-48b8-81e5-31bc820d1bc4.xml, display.ioctl_video_get_bank_select_code, ntddvdeo/IOCTL_VIDEO_GET_BANK_SELECT_CODE
f1_keywords:
 - "ntddvdeo/IOCTL_VIDEO_GET_BANK_SELECT_CODE"
 - "IOCTL_VIDEO_GET_BANK_SELECT_CODE"
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
- IOCTL_VIDEO_GET_BANK_SELECT_CODE
targetos: Windows
req.typenames: 
---

# IOCTL_VIDEO_GET_BANK_SELECT_CODE IOCTL


## -description



Returns a block of x86-specific executable code to be used by a high-resolution SVGA display driver for bank switching. Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers.




## -ioctlparameters




### -input-buffer

None


### -input-buffer-length








### -output-buffer

The miniport driver returns a VIDEO_BANK_SELECT structure in the VRP <b>OutputBuffer</b>.


### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

If the miniport driver returns its code block, it sets the <b>Information</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_status_block">STATUS_BLOCK</a> structure to <b>sizeof</b>(VIDEO_BANK_SELECT); otherwise, the miniport driver sets this member to zero.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_status_block">STATUS_BLOCK</a>
 

 

