---
UID: NS:ntddvdeo._VIDEO_PUBLIC_ACCESS_RANGES
title: _VIDEO_PUBLIC_ACCESS_RANGES (ntddvdeo.h)
description: The VIDEO_PUBLIC_ACCESS_RANGES structure contains information about video resources other than frame buffers and video RAM, such as memory-mapped I/O registers or ports.
old-location: display\video_public_access_ranges.htm
tech.root: display
ms.assetid: 78912da9-ab02-459c-97b0-477949d4a71d
ms.date: 05/10/2018
keywords: ["_VIDEO_PUBLIC_ACCESS_RANGES structure"]
ms.keywords: "*PVIDEO_PUBLIC_ACCESS_RANGES, PVIDEO_PUBLIC_ACCESS_RANGES, PVIDEO_PUBLIC_ACCESS_RANGES structure pointer [Display Devices], VIDEO_PUBLIC_ACCESS_RANGES, VIDEO_PUBLIC_ACCESS_RANGES structure [Display Devices], Video_Structs_5f4cdfd0-c59a-4568-9524-3f72416f7daf.xml, _VIDEO_PUBLIC_ACCESS_RANGES, display.video_public_access_ranges, ntddvdeo/PVIDEO_PUBLIC_ACCESS_RANGES, ntddvdeo/VIDEO_PUBLIC_ACCESS_RANGES"
f1_keywords:
 - "ntddvdeo/VIDEO_PUBLIC_ACCESS_RANGES"
 - "VIDEO_PUBLIC_ACCESS_RANGES"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddvdeo.h
api_name:
- VIDEO_PUBLIC_ACCESS_RANGES
product:
- Windows
targetos: Windows
req.typenames: VIDEO_PUBLIC_ACCESS_RANGES, *PVIDEO_PUBLIC_ACCESS_RANGES
---

# _VIDEO_PUBLIC_ACCESS_RANGES structure


## -description


The VIDEO_PUBLIC_ACCESS_RANGES structure contains information about video resources other than <a href="https://docs.microsoft.com/windows-hardware/drivers/">frame buffers</a> and video RAM, such as memory-mapped I/O registers or ports.


## -struct-fields

### -field InIoSpace

Indicates the location of the range. This parameter can be one of the following values, or certain bitwise combinations of these values:

|Value|Meaning|
|--- |--- |
|VIDEO_MEMORY_SPACE_DENSE|Obsolete.|
|VIDEO_MEMORY_SPACE_IO|The indicated address ranges are in system I/O space rather than in memory space.|
|VIDEO_MEMORY_SPACE_MEMORY|The indicated address ranges are in memory space rather than in system I/O space.|
|VIDEO_MEMORY_SPACE_P6CACHE|The processor aggregates a sequence of write operations and sends them to a given cache line. The processor then flushes the cache. This flag is meaningful only when VIDEO_MEMORY_SPACE_IO is not set.|
|VIDEO_MEMORY_SPACE_USER_MODE|Indicates that the address range specified should be mapped into user mode rather than kernel mode. This flag is meaningful only when VIDEO_MEMORY_SPACE_IO is not set.|

### -field MappedInIoSpace

Indicates, on the current platform, whether the registers or ports are mapped in I/O space or in memory space. A value of <b>TRUE</b> (1) indicates that the registers or ports are mapped in I/O space; a value of <b>FALSE</b> (0) indicates that the registers or ports are mapped in memory space.


### -field VirtualAddress

Pointer to the location of the registers or I/O ports as mapped under the current architecture.


## -remarks



VIDEO_PUBLIC_ACCESS_RANGES is similar to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_access_range">VIDEO_ACCESS_RANGE</a> in that both are used by miniport drivers to obtain information about display resources. The principal difference is that VIDEO_PUBLIC_ACCESS_RANGES contains information about control and accelerator registers for an adapter, while VIDEO_ACCESS_RANGE is used to hold frame buffer and video RAM addresses.

VIDEO_PUBLIC_ACCESS_RANGES is used as an input buffer with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvdeo/ni-ntddvdeo-ioctl_video_query_public_access_ranges">IOCTL_VIDEO_QUERY_PUBLIC_ACCESS_RANGES</a> request.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvdeo/ni-ntddvdeo-ioctl_video_query_public_access_ranges">IOCTL_VIDEO_QUERY_PUBLIC_ACCESS_RANGES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_access_range">VIDEO_ACCESS_RANGE</a>
 

 

