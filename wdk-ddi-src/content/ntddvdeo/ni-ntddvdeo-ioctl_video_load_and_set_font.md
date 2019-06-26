---
UID: NI:ntddvdeo.IOCTL_VIDEO_LOAD_AND_SET_FONT
title: IOCTL_VIDEO_LOAD_AND_SET_FONT (ntddvdeo.h)
description: Loads a user-defined font on the adapter. Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers.
old-location: display\ioctl_video_load_and_set_font.htm
tech.root: display
ms.assetid: 13771df5-f66c-4dd9-b2d3-4477fda82f8f
ms.date: 05/10/2018
ms.keywords: IOCTL_VIDEO_LOAD_AND_SET_FONT, IOCTL_VIDEO_LOAD_AND_SET_FONT control, IOCTL_VIDEO_LOAD_AND_SET_FONT control code [Display Devices], Video_IOCTLs_f68527dd-7070-4a47-91e2-9e64610508b7.xml, display.ioctl_video_load_and_set_font, ntddvdeo/IOCTL_VIDEO_LOAD_AND_SET_FONT
ms.topic: ioctl
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
- IOCTL_VIDEO_LOAD_AND_SET_FONT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_VIDEO_LOAD_AND_SET_FONT IOCTL


## -description



Loads a user-defined font on the adapter. Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers.




## -ioctlparameters




### -input-buffer

The VRP <b>InputBuffer</b> contains a VIDEO_LOAD_FONT_INFORMATION structure describing the font's width, height, and size, as well as a pointer to the font buffer.


### -input-buffer-length








### -output-buffer

None


### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

The miniport driver does not set the <b>Information</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/ns-video-_status_block">STATUS_BLOCK</a> structure.

