---
UID: NF:video.VideoPortMapDmaMemory
title: VideoPortMapDmaMemory function
author: windows-driver-content
description: The VideoPortMapDmaMemory function is obsolete in Windows 2000 and later.VideoPortMapDmaMemory maps a range of memory for use in DMA transfers.
old-location: display\videoportmapdmamemory.htm
old-project: display
ms.assetid: 51148c26-c10d-4c57-9e3e-c7d82d6a1c79
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: VideoPortMapDmaMemory, VideoPortMapDmaMemory function [Display Devices], VideoPort_Functions_f2a97e55-d165-4884-a121-52e98f8f46cd.xml, display.videoportmapdmamemory, video/VideoPortMapDmaMemory
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
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Videoprt.sys
apiname:
-	VideoPortMapDmaMemory
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortMapDmaMemory function


## -description


The <b>VideoPortMapDmaMemory</b> function is <b>obsolete</b> in Windows 2000 and later.

<b>VideoPortMapDmaMemory</b> maps a range of memory for use in DMA transfers.


## -syntax


````
PDMA VideoPortMapDmaMemory(
  _In_    PVOID                 HwDeviceExtension,
  _In_    PVIDEO_REQUEST_PACKET pVrp,
  _In_    PHYSICAL_ADDRESS      BoardAddress,
  _In_    PULONG                Length,
  _In_    PULONG                InIoSpace,
  _In_    PVOID                 MappedUserEvent,
  _In_    PVOID                 DisplayDriverEvent,
  _Inout_ PVOID                 *VirtualAddress
);
````


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param pVrp [in]

Pointer to a <a href="..\video\ns-video-_video_request_packet.md">VIDEO_REQUEST_PACKET</a>.


### -param BoardAddress [in]

Specifies the adapter's beginning address.


### -param Length [in]

Specifies the length, in bytes, of the range of memory.


### -param InIoSpace [in]

Indicates the location of the range. This parameter can be one of the following values:

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
Memory is densely mapped and linear.

</td>
</tr>
<tr>
<td>
VIDEO_MEMORY_SPACE_IO

</td>
<td>
The range is in system I/O space. Should not be set by the display driver.

</td>
</tr>
<tr>
<td>
VIDEO_MEMORY_SPACE_MEMORY

</td>
<td>
The range is in memory space. Should not be set by the display driver.

</td>
</tr>
<tr>
<td>
VIDEO_MEMORY_SPACE_P6CACHE

</td>
<td>
P6 MTRR caching, which is equivalent to write-combine caching. (kernel and user mode).

</td>
</tr>
<tr>
<td>
VIDEO_MEMORY_SPACE_USER_MODE

</td>
<td>
Memory pointer for application use.

</td>
</tr>
</table>
 


### -param MappedUserEvent [in]

Is reserved for system use.


### -param DisplayDriverEvent [in]

Is reserved for system use.


### -param VirtualAddress [in, out]

Is reserved for system use.


## -returns



<b>VideoPortMapDmaMemory</b> always returns <b>NULL</b>.




## -remarks



See <a href="https://msdn.microsoft.com/fe6c2e16-d222-4948-b1df-34ed8d57d9d8">Bus-Master DMA in Video Miniport Drivers</a> for information about packet-based and common-buffer DMA transfers.



