---
UID: NI:ntddvdeo.IOCTL_VIDEO_LOAD_AND_SET_FONT
title: IOCTL_VIDEO_LOAD_AND_SET_FONT
author: windows-driver-content
description: Loads a user-defined font on the adapter. Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers.
old-location: display\ioctl_video_load_and_set_font.htm
old-project: display
ms.assetid: 13771df5-f66c-4dd9-b2d3-4477fda82f8f
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.ioctl_video_load_and_set_font, IOCTL_VIDEO_LOAD_AND_SET_FONT control code [Display Devices], IOCTL_VIDEO_LOAD_AND_SET_FONT, ntddvdeo/IOCTL_VIDEO_LOAD_AND_SET_FONT, Video_IOCTLs_f68527dd-7070-4a47-91e2-9e64610508b7.xml
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ntddvdeo.h
apiname:
-	IOCTL_VIDEO_LOAD_AND_SET_FONT
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_LOAD_AND_SET_FONT IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



Loads a user-defined font on the adapter. Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers.




## -ioctlparameters




### -input-buffer

The VRP <b>InputBuffer</b> contains a VIDEO_LOAD_FONT_INFORMATION structure describing the font's width, height, and size, as well as a pointer to the font buffer.


### -input-buffer-length



<text></text>




### -output-buffer

None


### -output-buffer-length



<text></text>




### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The miniport driver does not set the <b>Information</b> member of the <a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a> structure.

