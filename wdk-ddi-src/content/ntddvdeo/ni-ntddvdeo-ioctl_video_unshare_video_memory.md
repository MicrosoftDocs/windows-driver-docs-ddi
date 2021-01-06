---
UID: NI:ntddvdeo.IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY
title: IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY (ntddvdeo.h)
description: Unmaps a video hardware frame buffer and video RAM from the virtual address space of the requester that was mapped by an IOCTL_VIDEO_SHARE_VIDEO_MEMORY request.
old-location: display\ioctl_video_unshare_video_memory.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY IOCTL"]
ms.keywords: IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY, IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY control, IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY control code [Display Devices], Video_IOCTLs_114ef264-3c3f-400d-bef0-4ebd2a4af035.xml, display.ioctl_video_unshare_video_memory, ntddvdeo/IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY
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
 - IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY
 - ntddvdeo/IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntddvdeo.h
api_name:
 - IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY
---

# IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY IOCTL


## -description

Unmaps a video hardware frame buffer and video RAM from the virtual address space of the requester that was mapped by an <a href="/windows-hardware/drivers/ddi/ntddvdeo/ni-ntddvdeo-ioctl_video_share_video_memory">IOCTL_VIDEO_SHARE_VIDEO_MEMORY</a> request.

## -ioctlparameters

### -input-buffer

The VRP <b>InputBuffer</b> contains a <a href="/windows-hardware/drivers/ddi/ntddvdeo/ns-ntddvdeo-_video_share_memory">VIDEO_SHARE_MEMORY</a> structure specifying the process and the virtual address where the video memory is mapped. The memory is unmapped by calling <a href="/windows-hardware/drivers/ddi/video/nf-video-videoportunmapmemory">VideoPortUnmapMemory</a>.

### -input-buffer-length

### -output-buffer

None

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

The miniport driver does not set the <b>Information</b> member of the <a href="/windows-hardware/drivers/ddi/video/ns-video-_status_block">STATUS_BLOCK</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddvdeo/ni-ntddvdeo-ioctl_video_share_video_memory">IOCTL_VIDEO_SHARE_VIDEO_MEMORY</a>



<a href="/windows-hardware/drivers/ddi/ntddvdeo/ns-ntddvdeo-_video_share_memory">VIDEO_SHARE_MEMORY</a>



<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportunmapmemory">VideoPortUnmapMemory</a>
