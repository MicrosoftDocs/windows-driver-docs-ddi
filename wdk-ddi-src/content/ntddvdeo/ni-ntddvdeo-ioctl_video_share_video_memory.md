---
UID: NI:ntddvdeo.IOCTL_VIDEO_SHARE_VIDEO_MEMORY
title: IOCTL_VIDEO_SHARE_VIDEO_MEMORY (ntddvdeo.h)
description: This IOCTL is called by a process that will share user-mode video memory as a linear frame buffer.
old-location: display\ioctl_video_share_video_memory.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["IOCTL_VIDEO_SHARE_VIDEO_MEMORY IOCTL"]
ms.keywords: IOCTL_VIDEO_SHARE_VIDEO_MEMORY, IOCTL_VIDEO_SHARE_VIDEO_MEMORY control, IOCTL_VIDEO_SHARE_VIDEO_MEMORY control code [Display Devices], Video_IOCTLs_90056f20-b995-4709-9923-1f7385ebfdce.xml, display.ioctl_video_share_video_memory, ntddvdeo/IOCTL_VIDEO_SHARE_VIDEO_MEMORY
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_VIDEO_SHARE_VIDEO_MEMORY
 - ntddvdeo/IOCTL_VIDEO_SHARE_VIDEO_MEMORY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddvdeo.h
api_name:
 - IOCTL_VIDEO_SHARE_VIDEO_MEMORY
---

# IOCTL_VIDEO_SHARE_VIDEO_MEMORY IOCTL


## -description

This IOCTL is called by a process that will share user-mode video memory as a linear <a href="/windows-hardware/drivers/">frame buffer</a>. Miniport drivers handle this IOCTL by mapping the frame buffer into the caller's address space with <a href="/windows-hardware/drivers/ddi/video/nf-video-videoportmapbankedmemory">VideoPortMapBankedMemory</a>. Otherwise this IOCTL is the same as <a href="/windows-hardware/drivers/ddi/ntddvdeo/ni-ntddvdeo-ioctl_video_map_video_memory">IOCTL_VIDEO_MAP_VIDEO_MEMORY</a>. 

This request is both modal and nonmodal: the miniport driver must return the location size of the frame buffer within video memory, and the frame buffer size and location can vary from mode to mode (modal characteristic), but a subsequent set-mode operation (to the same mode) must not cause the video memory to change location (nonmodal characteristic).

This IOCTL is DCI only.

## -ioctlparameters

### -input-buffer

The VRP <b>InputBuffer</b> contains a <a href="/windows-hardware/drivers/ddi/ntddvdeo/ns-ntddvdeo-_video_share_memory">VIDEO_SHARE_MEMORY</a> structure specifying a handle to the process mapping the frame buffer, and the requested view size and offset into the shared memory. The view size plus the offset must not exceed the memory size of the adapter.

### -input-buffer-length

### -output-buffer

The miniport driver returns the <a href="/windows-hardware/drivers/ddi/ntddvdeo/ns-ntddvdeo-_video_share_memory_information">VIDEO_SHARE_MEMORY_INFORMATION</a> structure in the VRP <b>OutputBuffer</b>. This output contains the virtual address where the video memory is mapped, the view size in bytes of the mapped memory and the offset into the view.

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

If the miniport driver successfully maps the memory, it sets the <b>Information</b> member of the <a href="/windows-hardware/drivers/ddi/video/ns-video-_status_block">STATUS_BLOCK</a> structure to <b>sizeof</b>(VIDEO_SHARE_MEMORY_INFORMATION); otherwise, the miniport driver sets this member to zero.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddvdeo/ni-ntddvdeo-ioctl_video_map_video_memory">IOCTL_VIDEO_MAP_VIDEO_MEMORY</a>



<a href="/windows-hardware/drivers/ddi/video/ns-video-_status_block">STATUS_BLOCK</a>



<a href="/windows-hardware/drivers/ddi/ntddvdeo/ns-ntddvdeo-_video_share_memory">VIDEO_SHARE_MEMORY</a>



<a href="/windows-hardware/drivers/ddi/ntddvdeo/ns-ntddvdeo-_video_share_memory_information">VIDEO_SHARE_MEMORY_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportmapbankedmemory">VideoPortMapBankedMemory</a>
