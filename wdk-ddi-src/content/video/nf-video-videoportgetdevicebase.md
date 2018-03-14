---
UID: NF:video.VideoPortGetDeviceBase
title: VideoPortGetDeviceBase function
author: windows-driver-content
description: The VideoPortGetDeviceBase function maps a range of bus-relative device memory or I/O addresses into system space.
old-location: display\videoportgetdevicebase.htm
old-project: display
ms.assetid: 53665c1d-8c0b-45c7-8d23-13c0964eda39
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: VideoPortGetDeviceBase, VideoPortGetDeviceBase function [Display Devices], VideoPort_Functions_ee5844a6-6337-42b7-b960-5228ad1c1ae4.xml, display.videoportgetdevicebase, video/VideoPortGetDeviceBase
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortGetDeviceBase
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortGetDeviceBase function


## -description


The <b>VideoPortGetDeviceBase</b> function maps a range of bus-relative device memory or I/O addresses into system space.


## -syntax


````
PVOID VideoPortGetDeviceBase(
   PVOID            HwDeviceExtension,
   PHYSICAL_ADDRESS IoAddress,
   ULONG            NumberOfUchars,
   UCHAR            InIoSpace
);
````


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's device extension.


### -param IoAddress

The base physical address of the range to map. You get this bus-relative value by calling <a href="..\video\nf-video-videoportgetdevicedata.md">VideoPortGetDeviceData</a>, <a href="..\video\nf-video-videoportgetregistryparameters.md">VideoPortGetRegistryParameters</a>, or <a href="..\video\nf-video-videoportgetaccessranges.md">VideoPortGetAccessRanges</a>. Otherwise, this value is a driver-supplied, default base address for the device memory or I/O ports.

You must have successfully claimed the range described by <i>IoAddress</i> and <i>NumberOfUchars</i> in the registry through a preceding call to <a href="..\video\nf-video-videoportverifyaccessranges.md">VideoPortVerifyAccessRanges</a> or <b>VideoPortGetAccessRanges</b>.


### -param NumberOfUchars

The number of bytes, starting at <i>IoAddress</i>, to map.


### -param InIoSpace

The location of the <i>IoAddress</i> range. This parameter can be one of the following flags or an ORed, compatible combination of these flags.

<table>
<tr>
<th>Flag</th>
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
The address range is in I/O space, not in memory space.

</td>
</tr>
<tr>
<td>
VIDEO_MEMORY_SPACE_MEMORY

</td>
<td>
The address range is in memory space, not in I/O space.

</td>
</tr>
<tr>
<td>
VIDEO_MEMORY_SPACE_P6CACHE

</td>
<td>
The processor aggregates a sequence of write operations, sends them to a cache line, and later flushes the cache. This flag is meaningful only when VIDEO_MEMORY_SPACE_IO is not set.

Designates the video memory as write-combined (WC). For information about WC caching, see the <a href="https://msdn.microsoft.com/library/windows/hardware/dn642116">Write-Combining Memory in Video Miniport Drivers</a> website article.

</td>
</tr>
</table>
 


## -returns



If successful, <b>VideoPortGetDeviceBase</b> returns the base virtual address of the mapping. If the specified bus-relative range cannot be mapped, <b>VideoPortGetDeviceBase</b> returns <b>NULL</b>.




## -remarks



You can pass the mapped virtual addresses to the <b>VideoPortRead</b><i>Xxx</i>, <b>VideoPortWrite</b><i>Xxx</i>, and <b>VideoPort</b><i>Xxx</i><b>Memory</b> functions, except for <a href="..\video\nf-video-videoportmapmemory.md">VideoPortMapMemory</a> and <a href="..\video\nf-video-videoportunmapmemory.md">VideoPortUnmapMemory</a>.

You must call <b>VideoPortGetDeviceBase</b> from the miniport driver's <a href="..\video\nc-video-pvideo_hw_find_adapter.md">HwVidFindAdapter</a>, <a href="..\video\nc-video-pminiport_query_device_routine.md">HwVidQueryDeviceCallback</a>, or <a href="..\video\nc-video-pminiport_get_registry_routine.md">HwVidQueryNamedValueCallback</a> function.

Before <i>HwVidFindAdapter</i> returns control, you should store both the mapped base address returned by <b>VideoPortGetDeviceBase</b> and the length of the mapped access range in the adapter's device extension (pointed to by <i>HwDeviceExtension</i>) for later use.

Access to the mapped address space must follow these rules:

<ul>
<li>
If <i>InIoSpace</i> is VIDEO_MEMORY_SPACE_IO, which indicates that the address is in I/O space, the virtual address that this function returns should be passed to the <b>VideoPortReadPort</b><i>Xxx</i>, <b>VideoPortWritePort</b><i>Xxx</i>, <b>VideoPortReadPortBuffer</b><i>Xxx</i>, and <b>VideoPortWritePortBuffer</b><i>Xxx</i> functions, where <i>Xxx</i> is <b>Uchar</b>, <b>Ushort</b>, or <b>Ulong</b>.

</li>
<li>
If <i>InIoSpace</i> is VIDEO_MEMORY_SPACE_MEMORY, which indicates that the address is not in I/O space but in memory space, the virtual address that this function returns should be passed to the <b>VideoPortReadRegister</b><i>Xxx</i>, <b>VideoPortWriteRegister</b><i>Xxx</i>, <b>VideoPortReadRegisterBuffer</b><i>Xxx</i>, and <b>VideoPortWriteRegisterBuffer</b><i>Xxx</i> functions, where <i>Xxx</i> is <b>Uchar</b>, <b>Ushort</b>, or <b>Ulong</b>.

</li>
<li>
The driver must not access addresses that are outside the range delimited by <i>NumberOfUchars</i>.

</li>
</ul>
<b>VideoPortGetDeviceBase</b> and <a href="..\video\nf-video-videoportmapmemory.md">VideoPortMapMemory</a> can both be called by the video miniport driver to map video memory into a virtual address space. If you call both of these functions to map the same physical addresses, or if you call one of the functions more than once to map the same physical addresses, you might have more than one virtual-address range that maps to the same physical-address range. In that case, you must set the VIDEO_MEMORY_SPACE_P6CACHE flag of the <i>InIoSpace</i> parameter to the same value in all of those calls.

Every universal memory architecture (UMA) display device uses a frame buffer that is located in main memory rather than on a PCI bus. In this case, do not call <b>VideoPortMapMemory</b> to map the frame buffer. To map a UMA frame buffer into system space, call <a href="..\wdm\nf-wdm-mmmapiospace.md">MmMapIoSpace</a>.

If a miniport driver does not support an adapter that it has mapped a logical range for, it must perform two steps before it returns control to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> function: call <a href="..\video\nf-video-videoportfreedevicebase.md">VideoPortFreeDeviceBase</a> to unmap the previously mapped range from system space, and call <a href="..\video\nf-video-videoportgetaccessranges.md">VideoPortGetAccessRanges</a> or <a href="..\video\nf-video-videoportverifyaccessranges.md">VideoPortVerifyAccessRanges</a> to release its claims on the range in the registry. 




## -see-also

<a href="..\video\nc-video-pvideo_hw_find_adapter.md">HwVidFindAdapter</a>



<a href="..\video\nf-video-videoportgetdevicedata.md">VideoPortGetDeviceData</a>



<a href="..\video\nf-video-videoportfreedevicebase.md">VideoPortFreeDeviceBase</a>



<a href="..\video\nf-video-videoportgetregistryparameters.md">VideoPortGetRegistryParameters</a>



<a href="..\video\nf-video-videoportzeromemory.md">VideoPortZeroMemory</a>



<a href="..\video\nf-video-videoportgetaccessranges.md">VideoPortGetAccessRanges</a>



<a href="..\video\nc-video-pminiport_get_registry_routine.md">HwVidQueryNamedValueCallback</a>



<a href="..\video\nc-video-pminiport_query_device_routine.md">HwVidQueryDeviceCallback</a>



<a href="..\video\nf-video-videoportcomparememory.md">VideoPortCompareMemory</a>



<a href="..\video\nf-video-videoportzerodevicememory.md">VideoPortZeroDeviceMemory</a>



<a href="..\video\nf-video-videoportverifyaccessranges.md">VideoPortVerifyAccessRanges</a>



<a href="..\video\nf-video-videoportmovememory.md">VideoPortMoveMemory</a>



 

 


