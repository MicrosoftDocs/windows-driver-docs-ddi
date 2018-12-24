---
UID: NS:ntddvdeo._VIDEO_SHARE_MEMORY_INFORMATION
title: "_VIDEO_SHARE_MEMORY_INFORMATION"
description: The VIDEO_SHARE_MEMORY_INFORMATION structure is used to communicate to the display driver that a request for a block of user-mode memory has been fulfilled.
old-location: display\video_share_memory_information.htm
tech.root: display
ms.assetid: 004ecb65-a462-45e5-a647-9655727b202b
ms.date: 05/10/2018
ms.keywords: "*PVIDEO_SHARE_MEMORY_INFORMATION, PVIDEO_SHARE_MEMORY_INFORMATION, PVIDEO_SHARE_MEMORY_INFORMATION structure pointer [Display Devices], VIDEO_SHARE_MEMORY_INFORMATION, VIDEO_SHARE_MEMORY_INFORMATION structure [Display Devices], Video_Structs_bed1b1c4-1ee2-4f6b-862e-d6dd85d11e35.xml, _VIDEO_SHARE_MEMORY_INFORMATION, display.video_share_memory_information, ntddvdeo/PVIDEO_SHARE_MEMORY_INFORMATION, ntddvdeo/VIDEO_SHARE_MEMORY_INFORMATION"
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
-	VIDEO_SHARE_MEMORY_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: VIDEO_SHARE_MEMORY_INFORMATION, *PVIDEO_SHARE_MEMORY_INFORMATION
---

# _VIDEO_SHARE_MEMORY_INFORMATION structure


## -description


The VIDEO_SHARE_MEMORY_INFORMATION structure is used to communicate to the display driver that a request for a block of user-mode memory has been fulfilled.


## -struct-fields




### -field SharedViewOffset

Indicates the offset, in bytes, from the beginning of the <a href="https://msdn.microsoft.com/f697e0db-1db0-4a81-94d8-0ca079885480">frame buffer</a>.


### -field SharedViewSize

Indicates the size, in bytes, of the frame buffer. The value of this member will always be a multiple of 64 KB.


### -field VirtualAddress

Indicates the address in virtual memory at which the requested memory was mapped.


## -remarks



When an application must have access to user-mode video memory, the display driver can call into the video miniport driver by sending it an <a href="https://msdn.microsoft.com/library/windows/hardware/ff568149">IOCTL_VIDEO_SHARE_VIDEO_MEMORY</a> request. The miniport driver uses a <a href="https://msdn.microsoft.com/library/windows/hardware/ff570548">VIDEO_SHARE_MEMORY</a> structure as an input buffer, and communicates back to the display driver a VIDEO_SHARE_MEMORY_INFORMATION structure. 

The video miniport driver fills out a VIDEO_SHARE_MEMORY_INFORMATION structure based on information in a VIDEO_SHARE_MEMORY structure. The following table summarizes how the information is used:

|VIDEO_SHARE_MEMORY member|Result on VIDEO_SHARE_MEMORY_INFORMATION|
|--- |--- |
|ProcessHandle|Is not used.|
|ViewOffset|Copied directly to SharedViewOffset.|
|ViewSize|Values that are multiples of 64 KB are copied directly to SharedViewSize. Other values are rounded up to the next larger multiple of 64 KB.|
|RequestedVirtualAddress|If NULL, the miniport driver determines the address of a frame buffer to assign to VirtualAddress. If non-NULL, the miniport driver attempts to assign that value to VirtualAddress.|
 
## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568149">IOCTL_VIDEO_SHARE_VIDEO_MEMORY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570548">VIDEO_SHARE_MEMORY</a>
 

 

