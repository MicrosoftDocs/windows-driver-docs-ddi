---
UID: NS:ntddvdeo._VIDEO_MEMORY
title: "_VIDEO_MEMORY" (ntddvdeo.h)
description: The VIDEO_MEMORY structure holds the address of a requested block of kernel-mode video memory.
old-location: display\video_memory.htm
tech.root: display
ms.assetid: 3d8b3b45-90d9-4e64-a52d-253c9cb86588
ms.date: 05/10/2018
ms.keywords: "*PVIDEO_MEMORY, PVIDEO_MEMORY, PVIDEO_MEMORY structure pointer [Display Devices], VIDEO_MEMORY, VIDEO_MEMORY structure [Display Devices], Video_Structs_85973586-1583-46cb-93a7-c8d37ba4ef5f.xml, _VIDEO_MEMORY, display.video_memory, ntddvdeo/PVIDEO_MEMORY, ntddvdeo/VIDEO_MEMORY"
ms.topic: struct
req.header: ntddvdeo.h
req.include-header: Ntddvdeo.h
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
-	ntddvdeo.h
api_name:
-	VIDEO_MEMORY
product:
- Windows
targetos: Windows
req.typenames: VIDEO_MEMORY, *PVIDEO_MEMORY
---

# _VIDEO_MEMORY structure


## -description


The VIDEO_MEMORY structure holds the address of a requested block of kernel-mode video memory.


## -struct-fields




### -field RequestedVirtualAddress

Pointer to the requested virtual address for either the video memory, or the base of video memory, depending on whether <a href="https://msdn.microsoft.com/library/windows/hardware/ff567812">IOCTL_VIDEO_MAP_VIDEO_MEMORY</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff568153">IOCTL_VIDEO_UNMAP_VIDEO_MEMORY</a> is using this structure.


## -remarks



VIDEO_MEMORY is used as an input structure to two IOCTLs: <a href="https://msdn.microsoft.com/library/windows/hardware/ff567812">IOCTL_VIDEO_MAP_VIDEO_MEMORY</a>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff568153">IOCTL_VIDEO_UNMAP_VIDEO_MEMORY</a>.

When VIDEO_MEMORY is used with IOCTL_VIDEO_MAP_VIDEO_MEMORY, <b>RequestedVirtualAddress</b> points to the requested virtual address for the video memory. In this case, the value is optional. If zero is specified, the operating system will choose an appropriate location.

When VIDEO_MEMORY is used with IOCTL_VIDEO_UNMAP_VIDEO_MEMORY, <b>RequestedVirtualAddress</b> points to the virtual address of the base of video memory. In this case, the size is implicit since it cannot change (you cannot add video memory dynamically, so it must be the same size as when it was mapped).

For structures used in mapping into user-mode video memory, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff570548">VIDEO_SHARE_MEMORY</a> AND <a href="https://msdn.microsoft.com/library/windows/hardware/ff570549">VIDEO_SHARE_MEMORY_INFORMATION</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567812">IOCTL_VIDEO_MAP_VIDEO_MEMORY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568153">IOCTL_VIDEO_UNMAP_VIDEO_MEMORY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570507">VIDEO_MEMORY_INFORMATION</a>
 

 

