---
UID: NF:video.VideoPortMapBankedMemory
title: VideoPortMapBankedMemory function (video.h)
description: The VideoPortMapBankedMemory function is obsolete, and is supported only for Windows NT 4.0 and previous drivers.
old-location: display\videoportmapbankedmemory.htm
tech.root: display
ms.assetid: ee94d883-b4c4-4cd5-9b61-2e51810f8fc8
ms.date: 05/10/2018
keywords: ["VideoPortMapBankedMemory function"]
ms.keywords: VideoPortMapBankedMemory, VideoPortMapBankedMemory function [Display Devices], VideoPort_Functions_14384264-da80-4c16-8de9-af143ac6a014.xml, display.videoportmapbankedmemory, video/VideoPortMapBankedMemory
f1_keywords:
 - "video/VideoPortMapBankedMemory"
 - "VideoPortMapBankedMemory"
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
- VideoPortMapBankedMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortMapBankedMemory function


## -description


The <b>VideoPortMapBankedMemory</b> function is <b>obsolete</b>, and is supported only for Windows NT 4.0 and previous drivers. Windows 2000 and later drivers must use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportmapmemory">VideoPortMapMemory</a>.

<b>VideoPortMapBankedMemory</b> remaps a bus-relative physical range of video memory into the corresponding display driver's virtual address space in response to a VRP with the <b>IoControlCode</b> member set to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvdeo/ni-ntddvdeo-ioctl_video_share_video_memory">IOCTL_VIDEO_SHARE_VIDEO_MEMORY</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvdeo/ni-ntddvdeo-ioctl_video_map_video_memory">IOCTL_VIDEO_MAP_VIDEO_MEMORY</a>. 


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's device extension.


### -param PhysicalAddress

Specifies the bus-relative base address of the range to be mapped.


### -param Length

Pointer to a variable specifying the total number of bytes of device memory to be mapped (regardless of bank size). <b>VideoPortMapBankedMemory</b> returns the actual size of the memory mapped, which can be rounded to a system-determined alignment boundary, in this parameter. However, the miniport and display drivers cannot access memory outside the range delimited by the input value at <i>Length</i>.


### -param InIoSpace

Indicates the location of the range. This parameter can be one of the following values:

|Value|Meaning|
|--- |--- |
|VIDEO_MEMORY_SPACE_DENSE|Obsolete|
|VIDEO_MEMORY_SPACE_IO|The range is in system I/O space rather than in memory space.|
|VIDEO_MEMORY_SPACE_MEMORY|The range is in memory space rather than in system I/O space.|
|VIDEO_MEMORY_SPACE_P6CACHE|The processor aggregates a sequence of write operations and sends them to a given cache line. The processor then flushes the cache. This flag is meaningful only when VIDEO_MEMORY_SPACE_IO is not set.|
|VIDEO_MEMORY_SPACE_USER_MODE|Indicates that the address range specified should be mapped into user mode rather than kernel mode. This flag is meaningful only when VIDEO_MEMORY_SPACE_IO is not set.|

### -param VirtualAddress

Is a handle to the process into which the memory must be mapped, or <b>NULL</b>. <b>NULL</b> specifies that the port driver should map the logical memory range at any location in the address space of the current process. Otherwise, this handle can be a value passed in a <a href="https://docs.microsoft.com/windows-hardware/drivers/">VRP</a> by the miniport driver's corresponding display driver. On return from a successful call, <b>VideoPortMapBankedMemory</b> resets the variable to the base virtual address to which it has mapped the given <i>PhysicalAddress</i>.


### -param BankLength

Specifies the size of a bank, in bytes.


### -param ReadWriteBank

If set to <b>TRUE</b> the bank is Read\Write; if set to <b>FALSE</b> there are two independent read and write banks. 


### -param BankRoutine

Pointer to a driver-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/display/">HwVidBankedMemoryCallback</a> function to be called by the Memory Manager when a new bank is accessed by the display driver.


### -param Context

Pointer to a miniport driver-supplied context that is passed back to the driver when the <i>BankRoutine</i> is called.


## -returns



<b>VideoPortMapBankedMemory</b> returns NO_ERROR if the given logical range was successfully mapped to a user-space virtual range. Otherwise, it can return ERROR_INVALID_PARAMETER.




## -remarks



<b>VideoPortMapBankedMemory</b> runs in kernel mode within the same context as the user-mode thread that initiated the call.

<b>VideoPortMapBankedMemory</b> is called by miniport drivers to efficiently manage x86 type devices that are limited to mapping a frame buffer in banks. When this routine returns to the caller, the frame buffer managed by the miniport driver is mapped as a linear frame buffer into the address space of the requesting process (see <i>VirtualAddress</i> parameter). When an access is made to an address in that mapped space, the Memory Manager calls the miniport driver to update the Bank Index Register to point to a new bank that contains the currently referenced address. The Bank Index Register is maintained by the miniport driver in <i>BankRoutine</i>. The correct Bank Index is calculated by the Memory Manager transparently to a display driver and passed to the miniport driver in the callback to <i>BankRoutine</i>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/display/">HwVidBankedMemoryCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvdeo/ni-ntddvdeo-ioctl_video_map_video_memory">IOCTL_VIDEO_MAP_VIDEO_MEMORY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvdeo/ni-ntddvdeo-ioctl_video_share_video_memory">IOCTL_VIDEO_SHARE_VIDEO_MEMORY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddvdeo/ni-ntddvdeo-ioctl_video_unshare_video_memory">IOCTL_VIDEO_UNSHARE_VIDEO_MEMORY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_request_packet">VIDEO_REQUEST_PACKET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportmapmemory">VideoPortMapMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportunmapmemory">VideoPortUnmapMemory</a>
 

 

