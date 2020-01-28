---
UID: NF:video.VideoPortGetDeviceBase
title: VideoPortGetDeviceBase function (video.h)
description: The VideoPortGetDeviceBase function maps a range of bus-relative device memory or I/O addresses into system space.
old-location: display\videoportgetdevicebase.htm
tech.root: display
ms.assetid: 53665c1d-8c0b-45c7-8d23-13c0964eda39
ms.date: 05/10/2018
ms.keywords: VideoPortGetDeviceBase, VideoPortGetDeviceBase function [Display Devices], VideoPort_Functions_ee5844a6-6337-42b7-b960-5228ad1c1ae4.xml, display.videoportgetdevicebase, video/VideoPortGetDeviceBase
f1_keywords:
 - "video/VideoPortGetDeviceBase"
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
- VideoPortGetDeviceBase
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortGetDeviceBase function


## -description


The <b>VideoPortGetDeviceBase</b> function maps a range of bus-relative device memory or I/O addresses into system space.


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's device extension.


### -param IoAddress

The base physical address of the range to map. You get this bus-relative value by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicedata">VideoPortGetDeviceData</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetregistryparameters">VideoPortGetRegistryParameters</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetaccessranges">VideoPortGetAccessRanges</a>. Otherwise, this value is a driver-supplied, default base address for the device memory or I/O ports.

You must have successfully claimed the range described by <i>IoAddress</i> and <i>NumberOfUchars</i> in the registry through a preceding call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportverifyaccessranges">VideoPortVerifyAccessRanges</a> or <b>VideoPortGetAccessRanges</b>.


### -param NumberOfUchars

The number of bytes, starting at <i>IoAddress</i>, to map.


### -param InIoSpace

The location of the <i>IoAddress</i> range. This parameter can be one of the following flags or an ORed, compatible combination of these flags.

| **Flag** | **Meaning** | 
|:--|:--|
| VIDEO_MEMORY_SPACE_DENSE | Obsolete. | 
| VIDEO_MEMORY_SPACE_IO | The address range is in I/O space, not in memory space. | 
| VIDEO_MEMORY_SPACE_MEMORY | The address range is in memory space, not in I/O space. | 
| VIDEO_MEMORY_SPACE_P6CACHE | The processor aggregates a sequence of write operations, sends them to a cache line, and later flushes the cache. This flag is meaningful only when VIDEO_MEMORY_SPACE_IO is not set. Designates the video memory as write-combined (WC). For information about WC caching, see the [Write-Combining Memory in Video Miniport Drivers](https://docs.microsoft.com/previous-versions/windows/hardware/design/dn642116(v=vs.85)) website article. | 

## -returns



If successful, <b>VideoPortGetDeviceBase</b> returns the base virtual address of the mapping. If the specified bus-relative range cannot be mapped, <b>VideoPortGetDeviceBase</b> returns <b>NULL</b>.




## -remarks



You can pass the mapped virtual addresses to the <b>VideoPortRead</b><i>Xxx</i>, <b>VideoPortWrite</b><i>Xxx</i>, and <b>VideoPort</b><i>Xxx</i><b>Memory</b> functions, except for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportmapmemory">VideoPortMapMemory</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportunmapmemory">VideoPortUnmapMemory</a>.

You must call <b>VideoPortGetDeviceBase</b> from the miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_find_adapter">HwVidFindAdapter</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pminiport_query_device_routine">HwVidQueryDeviceCallback</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pminiport_get_registry_routine">HwVidQueryNamedValueCallback</a> function.

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
<b>VideoPortGetDeviceBase</b> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportmapmemory">VideoPortMapMemory</a> can both be called by the video miniport driver to map video memory into a virtual address space. If you call both of these functions to map the same physical addresses, or if you call one of the functions more than once to map the same physical addresses, you might have more than one virtual-address range that maps to the same physical-address range. In that case, you must set the VIDEO_MEMORY_SPACE_P6CACHE flag of the <i>InIoSpace</i> parameter to the same value in all of those calls.

Every universal memory architecture (UMA) display device uses a frame buffer that is located in main memory rather than on a PCI bus. In this case, do not call <b>VideoPortMapMemory</b> to map the frame buffer. To map a UMA frame buffer into system space, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-mmmapiospace">MmMapIoSpace</a>.

If a miniport driver does not support an adapter that it has mapped a logical range for, it must perform two steps before it returns control to the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> function: call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportfreedevicebase">VideoPortFreeDeviceBase</a> to unmap the previously mapped range from system space, and call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetaccessranges">VideoPortGetAccessRanges</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportverifyaccessranges">VideoPortVerifyAccessRanges</a> to release its claims on the range in the registry. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_find_adapter">HwVidFindAdapter</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pminiport_query_device_routine">HwVidQueryDeviceCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pminiport_get_registry_routine">HwVidQueryNamedValueCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportcomparememory">VideoPortCompareMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportfreedevicebase">VideoPortFreeDeviceBase</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetaccessranges">VideoPortGetAccessRanges</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicedata">VideoPortGetDeviceData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetregistryparameters">VideoPortGetRegistryParameters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportmovememory">VideoPortMoveMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportverifyaccessranges">VideoPortVerifyAccessRanges</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportzerodevicememory">VideoPortZeroDeviceMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportzeromemory">VideoPortZeroMemory</a>
 

 

