---
UID: NI:ntddvdeo.IOCTL_VIDEO_SET_CURSOR_POSITION
title: IOCTL_VIDEO_SET_CURSOR_POSITION
author: windows-driver-content
description: Sets the cursor position (row and column). Miniport drivers for VGA-compatible adapters are required to support this request, which is modal. It is optional for other miniport drivers.
old-location: display\ioctl_video_set_cursor_position.htm
tech.root: display
ms.assetid: 80346b99-49f5-4cbf-b524-1c5f40cf441f
ms.date: 5/10/2018
ms.keywords: IOCTL_VIDEO_SET_CURSOR_POSITION, IOCTL_VIDEO_SET_CURSOR_POSITION control, IOCTL_VIDEO_SET_CURSOR_POSITION control code [Display Devices], Video_IOCTLs_f95d8cf3-a53e-4b67-867e-7af83e3b0d40.xml, display.ioctl_video_set_cursor_position, ntddvdeo/IOCTL_VIDEO_SET_CURSOR_POSITION
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddvdeo.h
api_name:
-	IOCTL_VIDEO_SET_CURSOR_POSITION
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_VIDEO_SET_CURSOR_POSITION IOCTL


## -description



Sets the cursor position (row and column). Miniport drivers for VGA-compatible adapters are required to support this request, which is modal. It is optional for other miniport drivers.




## -ioctlparameters




### -input-buffer

The VRP <b>InputBuffer</b> contains the VIDEO_CURSOR_POSITION structure to be set.


### -input-buffer-length








### -output-buffer

None


### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

The miniport driver does not set the <b>Information</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff569732">STATUS_BLOCK</a> structure.

