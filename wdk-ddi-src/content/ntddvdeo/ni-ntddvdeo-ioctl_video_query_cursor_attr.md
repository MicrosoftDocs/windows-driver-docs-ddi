---
UID: NI:ntddvdeo.IOCTL_VIDEO_QUERY_CURSOR_ATTR
title: IOCTL_VIDEO_QUERY_CURSOR_ATTR
author: windows-driver-content
description: Returns the size, position, and visibility of the cursor.
old-location: display\ioctl_video_query_cursor_attr.htm
tech.root: display
ms.assetid: c4ec2813-3e5f-401d-8ad4-cd0682e15e5b
ms.date: 5/10/2018
ms.keywords: IOCTL_VIDEO_QUERY_CURSOR_ATTR, IOCTL_VIDEO_QUERY_CURSOR_ATTR control, IOCTL_VIDEO_QUERY_CURSOR_ATTR control code [Display Devices], Video_IOCTLs_5c88c1de-006e-4141-9dcd-59d03d51755f.xml, display.ioctl_video_query_cursor_attr, ntddvdeo/IOCTL_VIDEO_QUERY_CURSOR_ATTR
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
-	IOCTL_VIDEO_QUERY_CURSOR_ATTR
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_VIDEO_QUERY_CURSOR_ATTR IOCTL


## -description



Returns the size, position, and visibility of the cursor. Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers. The cursor position is specified by top and bottom scan lines, instead of row and column information, for VGA-compatible adapters.




## -ioctlparameters




### -input-buffer

None


### -input-buffer-length








### -output-buffer

The miniport driver returns a VIDEO_CURSOR_ATTRIBUTES structure in the VRP <b>OutputBuffer</b>.


### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

If the miniport driver successfully returns the cursor-attribute data, it sets the <b>Information</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff569732">STATUS_BLOCK</a> structure to <b>sizeof</b>(VIDEO_CURSOR_ATTRIBUTES); otherwise, the miniport driver sets this member to zero.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff569732">STATUS_BLOCK</a>
 

 

