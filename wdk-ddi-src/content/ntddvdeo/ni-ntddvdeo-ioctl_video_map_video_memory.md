---
UID: NI:ntddvdeo.IOCTL_VIDEO_MAP_VIDEO_MEMORY
title: IOCTL_VIDEO_MAP_VIDEO_MEMORY
author: windows-driver-content
description: Maps the video hardware frame buffer and video RAM into the virtual address space of the requester.
old-location: display\ioctl_video_map_video_memory.htm
old-project: display
ms.assetid: 9e17502a-b5bf-4f17-8e74-1974f7e65e01
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS, TAPE_WRITE_MARKS
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
req.alt-api: IOCTL_VIDEO_MAP_VIDEO_MEMORY
req.alt-loc: Ntddvdeo.h
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
req.typenames: *PTAPE_WRITE_MARKS, TAPE_WRITE_MARKS
---

# IOCTL_VIDEO_MAP_VIDEO_MEMORY IOCTL



## -description

Maps the video hardware <a href="wdkgloss.f#wdkgloss.frame_buffer#wdkgloss.frame_buffer"><i>frame buffer</i></a> and video RAM into the virtual address space of the requester. Miniport drivers are required to handle this IOCTL and to map all video memory in the caller's address space with <a href="..\video\nf-video-videoportmapmemory.md">VideoPortMapMemory</a>. 

This request is both modal and nonmodal: the miniport driver must return the location size of the frame buffer within video memory, and the frame buffer size and location can vary from mode to mode (modal characteristic). However, a subsequent set-mode operation (to the same mode) must not cause the video memory to change location (nonmodal characteristic).



Maps the video hardware <a href="wdkgloss.f#wdkgloss.frame_buffer#wdkgloss.frame_buffer"><i>frame buffer</i></a> and video RAM into the virtual address space of the requester. Miniport drivers are required to handle this IOCTL and to map all video memory in the caller's address space with <a href="..\video\nf-video-videoportmapmemory.md">VideoPortMapMemory</a>. 

This request is both modal and nonmodal: the miniport driver must return the location size of the frame buffer within video memory, and the frame buffer size and location can vary from mode to mode (modal characteristic). However, a subsequent set-mode operation (to the same mode) must not cause the video memory to change location (nonmodal characteristic).



## -ioctlparameters

### -input-buffer
The VRP <b>InputBuffer</b> contains a <a href="..\ntddvdeo\ns-ntddvdeo-_video_memory.md">VIDEO_MEMORY</a> structure specifying either a requested virtual base address or zero, which requests the system to assign a virtual base address mapped to the adapter's RAM and frame buffer range(s).


### -input-buffer-length

<text></text>

### -output-buffer
The miniport driver returns a <a href="..\ntddvdeo\ns-ntddvdeo-_video_memory_information.md">VIDEO_MEMORY_INFORMATION</a> structure in the VRP <b>OutputBuffer</b>.


### -output-buffer-length

<text></text>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the miniport driver successfully maps the memory, it sets the <b>Information</b> member of the <a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a> structure to <b>sizeof</b>(VIDEO_MEMORY_INFORMATION); otherwise, it sets this member to zero.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\video\nf-video-videoportmapmemory.md">VideoPortMapMemory</a>
</dt>
<dt>
<a href="..\ntddvdeo\ns-ntddvdeo-_video_memory.md">VIDEO_MEMORY</a>
</dt>
<dt>
<a href="..\ntddvdeo\ns-ntddvdeo-_video_memory_information.md">VIDEO_MEMORY_INFORMATION</a>
</dt>
<dt>
<a href="..\video\ns-video-_status_block.md">STATUS_BLOCK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20IOCTL_VIDEO_MAP_VIDEO_MEMORY control code%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

