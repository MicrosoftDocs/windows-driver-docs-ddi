---
UID: NI:ntddvdeo.IOCTL_VIDEO_UNMAP_VIDEO_MEMORY
title: IOCTL_VIDEO_UNMAP_VIDEO_MEMORY (ntddvdeo.h)
description: Releases a mapping between the virtual address space and the adapter's frame buffer and video RAM. Miniport drivers are required to support this nonmodal request.
old-location: display\ioctl_video_unmap_video_memory.htm
tech.root: display
ms.assetid: 421cbe15-f2a6-495d-90f2-09a13771d018
ms.date: 05/10/2018
ms.keywords: IOCTL_VIDEO_UNMAP_VIDEO_MEMORY, IOCTL_VIDEO_UNMAP_VIDEO_MEMORY control, IOCTL_VIDEO_UNMAP_VIDEO_MEMORY control code [Display Devices], Video_IOCTLs_97fad6e5-d6e7-4487-84ab-cee66609ccd9.xml, display.ioctl_video_unmap_video_memory, ntddvdeo/IOCTL_VIDEO_UNMAP_VIDEO_MEMORY
ms.topic: ioctl
f1_keywords:
 - "ntddvdeo/IOCTL_VIDEO_UNMAP_VIDEO_MEMORY"
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
- IOCTL_VIDEO_UNMAP_VIDEO_MEMORY
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_VIDEO_UNMAP_VIDEO_MEMORY IOCTL


## -description



Releases a mapping between the virtual address space and the adapter's <a href="https://docs.microsoft.com/windows-hardware/drivers/">frame buffer</a> and video RAM. Miniport drivers are required to support this nonmodal request.




## -ioctlparameters




### -input-buffer

The VRP <b>InputBuffer</b> contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvdeo/ns-ntddvdeo-_video_memory">VIDEO_MEMORY</a> structure, specifying the previously mapped virtual base address to be released with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportunmapmemory">VideoPortUnmapMemory</a>.


### -input-buffer-length








### -output-buffer

None


### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

The miniport driver does not set the <b>Information</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_status_block">STATUS_BLOCK</a> structure.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvdeo/ns-ntddvdeo-_video_memory">VIDEO_MEMORY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportunmapmemory">VideoPortUnmapMemory</a>
 

 

