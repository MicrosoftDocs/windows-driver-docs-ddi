---
UID: NS:ntddvdeo._VIDEO_PUBLIC_ACCESS_RANGES
title: "_VIDEO_PUBLIC_ACCESS_RANGES"
author: windows-driver-content
description: The VIDEO_PUBLIC_ACCESS_RANGES structure contains information about video resources other than frame buffers and video RAM, such as memory-mapped I/O registers or ports.
old-location: display\video_public_access_ranges.htm
old-project: display
ms.assetid: 78912da9-ab02-459c-97b0-477949d4a71d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PVIDEO_PUBLIC_ACCESS_RANGES, PVIDEO_PUBLIC_ACCESS_RANGES, PVIDEO_PUBLIC_ACCESS_RANGES structure pointer [Display Devices], VIDEO_PUBLIC_ACCESS_RANGES, VIDEO_PUBLIC_ACCESS_RANGES structure [Display Devices], Video_Structs_5f4cdfd0-c59a-4568-9524-3f72416f7daf.xml, _VIDEO_PUBLIC_ACCESS_RANGES, display.video_public_access_ranges, ntddvdeo/PVIDEO_PUBLIC_ACCESS_RANGES, ntddvdeo/VIDEO_PUBLIC_ACCESS_RANGES"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	VIDEO_PUBLIC_ACCESS_RANGES
product: Windows
targetos: Windows
req.typenames: VIDEO_PUBLIC_ACCESS_RANGES, *PVIDEO_PUBLIC_ACCESS_RANGES
---

# _VIDEO_PUBLIC_ACCESS_RANGES structure


## -description


The VIDEO_PUBLIC_ACCESS_RANGES structure contains information about video resources other than <a href="https://msdn.microsoft.com/f697e0db-1db0-4a81-94d8-0ca079885480">frame buffers</a> and video RAM, such as memory-mapped I/O registers or ports.


## -struct-fields




### -field InIoSpace

Indicates the location of the range. This parameter can be one of the following values, or certain bitwise combinations of these values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
VIDEO_MEMORY_SPACE_DENSE

</td>
<td>
Obsolete.

</td>
</tr>
<tr>
<td>
VIDEO_MEMORY_SPACE_IO

</td>
<td>
The indicated address ranges are in system I/O space rather than in memory space.

</td>
</tr>
<tr>
<td>
VIDEO_MEMORY_SPACE_MEMORY

</td>
<td>
The indicated address ranges are in memory space rather than in system I/O space. 

</td>
</tr>
<tr>
<td>
VIDEO_MEMORY_SPACE_P6CACHE

</td>
<td>
The processor aggregates a sequence of write operations and sends them to a given cache line. The processor then flushes the cache. This flag is meaningful only when VIDEO_MEMORY_SPACE_IO is not set.

</td>
</tr>
<tr>
<td>
VIDEO_MEMORY_SPACE_USER_MODE

</td>
<td>
Indicates that the address range specified should be mapped into user mode rather than kernel mode. This flag is meaningful only when VIDEO_MEMORY_SPACE_IO is not set.

</td>
</tr>
</table>
 


### -field MappedInIoSpace

Indicates, on the current platform, whether the registers or ports are mapped in I/O space or in memory space. A value of <b>TRUE</b> (1) indicates that the registers or ports are mapped in I/O space; a value of <b>FALSE</b> (0) indicates that the registers or ports are mapped in memory space.


### -field VirtualAddress

Pointer to the location of the registers or I/O ports as mapped under the current architecture.


## -remarks



VIDEO_PUBLIC_ACCESS_RANGES is similar to <a href="https://msdn.microsoft.com/library/windows/hardware/ff570498">VIDEO_ACCESS_RANGE</a> in that both are used by miniport drivers to obtain information about display resources. The principal difference is that VIDEO_PUBLIC_ACCESS_RANGES contains information about control and accelerator registers for an adapter, while VIDEO_ACCESS_RANGE is used to hold frame buffer and video RAM addresses.

VIDEO_PUBLIC_ACCESS_RANGES is used as an input buffer with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567829">IOCTL_VIDEO_QUERY_PUBLIC_ACCESS_RANGES</a> request.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff567829">IOCTL_VIDEO_QUERY_PUBLIC_ACCESS_RANGES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570498">VIDEO_ACCESS_RANGE</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VIDEO_PUBLIC_ACCESS_RANGES structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

