---
UID: NI:ntddvdeo.IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY
title: IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY
author: windows-driver-content
description: Unmaps a video hardware frame buffer and video RAM from the virtual address space of the requester that was mapped by an IOCTL_VIDEO_SHARE_VIDEO_MEMORY request.
old-location: display\ioctl_video_unshare_video_memory.htm
old-project: display
ms.assetid: f6ec4237-05f1-4777-a035-7cedb4283e0e
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY, IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY control, IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY control code [Display Devices], Video_IOCTLs_114ef264-3c3f-400d-bef0-4ebd2a4af035.xml, display.ioctl_video_unshare_video_memory, ntddvdeo/IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY
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
-	IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY
product: Windows
targetos: Windows
req.typenames: 
---

# IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY IOCTL


## -description



Unmaps a video hardware frame buffer and video RAM from the virtual address space of the requester that was mapped by an <a href="https://msdn.microsoft.com/library/windows/hardware/ff568149">IOCTL_VIDEO_SHARE_VIDEO_MEMORY</a> request.




## -ioctlparameters




### -input-buffer

The VRP <b>InputBuffer</b> contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570548">VIDEO_SHARE_MEMORY</a> structure specifying the process and the virtual address where the video memory is mapped. The memory is unmapped by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff570376">VideoPortUnmapMemory</a>.


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

The miniport driver does not set the <b>Information</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff569732">STATUS_BLOCK</a> structure.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568149">IOCTL_VIDEO_SHARE_VIDEO_MEMORY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570548">VIDEO_SHARE_MEMORY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570376">VideoPortUnmapMemory</a>
 

 

