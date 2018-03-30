---
UID: NI:ntddvdeo.IOCTL_VIDEO_QUERY_CURSOR_POSITION
title: IOCTL_VIDEO_QUERY_CURSOR_POSITION
author: windows-driver-content
description: Returns the current cursor position (row and column). Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers.
old-location: display\ioctl_video_query_cursor_position.htm
old-project: display
ms.assetid: 0ca9aa92-7b9f-4fd4-a41e-663ac1aa5799
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IOCTL_VIDEO_QUERY_CURSOR_POSITION, IOCTL_VIDEO_QUERY_CURSOR_POSITION control code [Display Devices], Video_IOCTLs_f9790f8c-b853-4231-b058-a09bd42e15de.xml, display.ioctl_video_query_cursor_position, ntddvdeo/IOCTL_VIDEO_QUERY_CURSOR_POSITION
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ntddvdeo.h
api_name:
-	IOCTL_VIDEO_QUERY_CURSOR_POSITION
product: Windows
targetos: Windows
req.typenames: TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS
---

# IOCTL_VIDEO_QUERY_CURSOR_POSITION IOCTL


## -description



Returns the current cursor position (row and column). Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers.




## -ioctlparameters




### -input-buffer

None


### -input-buffer-length



<text></text>




### -output-buffer

The miniport driver returns a VIDEO_CURSOR_POSITION structure in the VRP <b>OutputBuffer</b>.


### -output-buffer-length



<text></text>




### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

If the miniport driver successfully returns the cursor position, it sets the <b>Information</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff569732">STATUS_BLOCK</a> structure to <b>sizeof</b>(VIDEO_CURSOR_POSITION); otherwise, the miniport driver sets this member to zero.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff569732">STATUS_BLOCK</a>
 

 

