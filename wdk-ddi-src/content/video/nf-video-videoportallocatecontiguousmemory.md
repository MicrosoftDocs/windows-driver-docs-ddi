---
UID: NF:video.VideoPortAllocateContiguousMemory
title: VideoPortAllocateContiguousMemory function
author: windows-driver-content
description: The VideoPortAllocateContiguousMemory function is obsolete in Windows 2000 and later.
old-location: display\videoportallocatecontiguousmemory.htm
old-project: display
ms.assetid: ba23f4d4-7e3d-4bfc-acf7-68dab01d2f61
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: VideoPort_Functions_5aed176c-b0d1-4b0d-8d0d-7689bc31d661.xml, video/VideoPortAllocateContiguousMemory, VideoPortAllocateContiguousMemory function [Display Devices], display.videoportallocatecontiguousmemory, VideoPortAllocateContiguousMemory
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Videoprt.sys
apiname:
-	VideoPortAllocateContiguousMemory
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortAllocateContiguousMemory function


## -description


The <b>VideoPortAllocateContiguousMemory</b> function is <b>obsolete</b> in Windows 2000 and later. Video miniport drivers should use <a href="..\video\nf-video-videoportallocatecommonbuffer.md">VideoPortAllocateCommonBuffer</a> in its place.

<b>VideoPortAllocateContiguousMemory</b> allocates a range of physically contiguous, cache-aligned memory from the nonpaged pool.


## -syntax


````
PVOID VideoPortAllocateContiguousMemory(
  _In_ PVOID            HwDeviceExtension,
  _In_ ULONG            NumberOfBytes,
  _In_ PHYSICAL_ADDRESS HighestAcceptableAddress
);
````


## -parameters




#### - HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


#### - NumberOfBytes [in]

Specifies the size in bytes of the block of contiguous memory to be allocated. 


#### - HighestAcceptableAddress [in]

Specifies the highest valid physical address the miniport driver can use. For example, if a device can only reference physical memory in the lower 16MB, this value would be set to 0x00000000FFFFFF.


## -returns


<b>VideoPortAllocateContiguousMemory</b> returns the base virtual address for the allocated memory, if the call is successful. If the request cannot be satisfied, <b>NULL</b> is returned.



## -remarks


<b>VideoPortAllocateContiguousMemory</b> can be called to allocate a contiguous block of physical memory for a long-term internal buffer.

A miniport driver that must use contiguous memory should allocate only what it needs during driver initialization because nonpaged pool is likely to become fragmented as the system runs. If the miniport driver is unloaded, it must deallocate the memory. Contiguous allocations are aligned on an integral multiple of the processor's data-cache-line size to prevent cache and coherency problems.



## -see-also

<a href="..\video\nf-video-videoportallocatebuffer.md">VideoPortAllocateBuffer</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortAllocateContiguousMemory function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

