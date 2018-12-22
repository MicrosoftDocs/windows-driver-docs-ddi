---
UID: NI:ntddvdeo.IOCTL_VIDEO_MAP_VIDEO_MEMORY
title: IOCTL_VIDEO_MAP_VIDEO_MEMORY
description: Maps the video hardware frame buffer and video RAM into the virtual address space of the requester.
old-location: display\ioctl_video_map_video_memory.htm
tech.root: display
ms.assetid: 9e17502a-b5bf-4f17-8e74-1974f7e65e01
ms.date: 05/10/2018
ms.keywords: IOCTL_VIDEO_MAP_VIDEO_MEMORY, IOCTL_VIDEO_MAP_VIDEO_MEMORY control, IOCTL_VIDEO_MAP_VIDEO_MEMORY control code [Display Devices], Video_IOCTLs_8a343fc8-9ebe-4079-a175-94d39222adee.xml, display.ioctl_video_map_video_memory, ntddvdeo/IOCTL_VIDEO_MAP_VIDEO_MEMORY
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
-	IOCTL_VIDEO_MAP_VIDEO_MEMORY
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_VIDEO_MAP_VIDEO_MEMORY IOCTL


## -description



Maps the video hardware <a href="https://msdn.microsoft.com/f697e0db-1db0-4a81-94d8-0ca079885480">frame buffer</a> and video RAM into the virtual address space of the requester. Miniport drivers are required to handle this IOCTL and to map all video memory in the caller's address space with <a href="https://msdn.microsoft.com/library/windows/hardware/ff570331">VideoPortMapMemory</a>. 

This request is both modal and nonmodal: the miniport driver must return the location size of the frame buffer within video memory, and the frame buffer size and location can vary from mode to mode (modal characteristic). However, a subsequent set-mode operation (to the same mode) must not cause the video memory to change location (nonmodal characteristic).




## -ioctlparameters




### -input-buffer

The VRP <b>InputBuffer</b> contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570506">VIDEO_MEMORY</a> structure specifying either a requested virtual base address or zero, which requests the system to assign a virtual base address mapped to the adapter's RAM and frame buffer range(s).


### -input-buffer-length








### -output-buffer

The miniport driver returns a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570507">VIDEO_MEMORY_INFORMATION</a> structure in the VRP <b>OutputBuffer</b>.


### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

If the miniport driver successfully maps the memory, it sets the <b>Information</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff569732">STATUS_BLOCK</a> structure to <b>sizeof</b>(VIDEO_MEMORY_INFORMATION); otherwise, it sets this member to zero.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff569732">STATUS_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570506">VIDEO_MEMORY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570507">VIDEO_MEMORY_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570331">VideoPortMapMemory</a>
 

 

