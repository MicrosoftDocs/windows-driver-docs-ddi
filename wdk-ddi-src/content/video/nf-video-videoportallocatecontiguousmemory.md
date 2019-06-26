---
UID: NF:video.VideoPortAllocateContiguousMemory
title: VideoPortAllocateContiguousMemory function (video.h)
description: The VideoPortAllocateContiguousMemory function is obsolete in Windows 2000 and later.
old-location: display\videoportallocatecontiguousmemory.htm
tech.root: display
ms.assetid: ba23f4d4-7e3d-4bfc-acf7-68dab01d2f61
ms.date: 05/10/2018
ms.keywords: VideoPortAllocateContiguousMemory, VideoPortAllocateContiguousMemory function [Display Devices], VideoPort_Functions_5aed176c-b0d1-4b0d-8d0d-7689bc31d661.xml, display.videoportallocatecontiguousmemory, video/VideoPortAllocateContiguousMemory
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Videoprt.sys
api_name:
- VideoPortAllocateContiguousMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortAllocateContiguousMemory function


## -description


The <b>VideoPortAllocateContiguousMemory</b> function is <b>obsolete</b> in Windows 2000 and later. Video miniport drivers should use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportallocatecommonbuffer">VideoPortAllocateCommonBuffer</a> in its place.

<b>VideoPortAllocateContiguousMemory</b> allocates a range of physically contiguous, cache-aligned memory from the nonpaged pool.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param NumberOfBytes [in]

Specifies the size in bytes of the block of contiguous memory to be allocated. 


### -param HighestAcceptableAddress [in]

Specifies the highest valid physical address the miniport driver can use. For example, if a device can only reference physical memory in the lower 16MB, this value would be set to 0x00000000FFFFFF.


## -returns



<b>VideoPortAllocateContiguousMemory</b> returns the base virtual address for the allocated memory, if the call is successful. If the request cannot be satisfied, <b>NULL</b> is returned.




## -remarks



<b>VideoPortAllocateContiguousMemory</b> can be called to allocate a contiguous block of physical memory for a long-term internal buffer.

A miniport driver that must use contiguous memory should allocate only what it needs during driver initialization because nonpaged pool is likely to become fragmented as the system runs. If the miniport driver is unloaded, it must deallocate the memory. Contiguous allocations are aligned on an integral multiple of the processor's data-cache-line size to prevent cache and coherency problems.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportallocatebuffer">VideoPortAllocateBuffer</a>
 

 

