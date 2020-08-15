---
UID: NF:video.VideoPortMapDmaMemory
title: VideoPortMapDmaMemory function (video.h)
description: The VideoPortMapDmaMemory function is obsolete in Windows 2000 and later.VideoPortMapDmaMemory maps a range of memory for use in DMA transfers.
old-location: display\videoportmapdmamemory.htm
tech.root: display
ms.assetid: 51148c26-c10d-4c57-9e3e-c7d82d6a1c79
ms.date: 05/10/2018
keywords: ["VideoPortMapDmaMemory function"]
ms.keywords: VideoPortMapDmaMemory, VideoPortMapDmaMemory function [Display Devices], VideoPort_Functions_f2a97e55-d165-4884-a121-52e98f8f46cd.xml, display.videoportmapdmamemory, video/VideoPortMapDmaMemory
f1_keywords:
 - "video/VideoPortMapDmaMemory"
 - "VideoPortMapDmaMemory"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Videoprt.sys
api_name:
- VideoPortMapDmaMemory
targetos: Windows
req.typenames: 
---

# VideoPortMapDmaMemory function

## -description

The <b>VideoPortMapDmaMemory</b> function is <b>obsolete</b> in Windows 2000 and later.

<b>VideoPortMapDmaMemory</b> maps a range of memory for use in DMA transfers.

## -parameters

### -param HwDeviceExtension 
[in]
Pointer to the miniport driver's device extension.


### -param pVrp 
[in]
Pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_request_packet">VIDEO_REQUEST_PACKET</a>.

### -param BoardAddress 
[in]
Specifies the adapter's beginning address.

### -param Length 
[in]
Specifies the length, in bytes, of the range of memory.

### -param InIoSpace 
[in]
Indicates the location of the range. This parameter can be one of the following values:

|Value|Meaning|
|--- |--- |
|VIDEO_MEMORY_SPACE_DENSE|Memory is densely mapped and linear.|
|VIDEO_MEMORY_SPACE_IO|The range is in system I/O space. Should not be set by the display driver.|
|VIDEO_MEMORY_SPACE_MEMORY|The range is in memory space. Should not be set by the display driver.|
|VIDEO_MEMORY_SPACE_P6CACHE|P6 MTRR caching, which is equivalent to write-combine caching. (kernel and user mode).|
|VIDEO_MEMORY_SPACE_USER_MODE|Memory pointer for application use.|

### -param MappedUserEvent 
[in]
Is reserved for system use.

### -param DisplayDriverEvent 
[in]
Is reserved for system use.

### -param VirtualAddress 
[in, out]
Is reserved for system use.

## -returns

<b>VideoPortMapDmaMemory</b> always returns <b>NULL</b>.

## -remarks

See <a href="https://docs.microsoft.com/windows-hardware/drivers/display/bus-master-dma-in-video-miniport-drivers">Bus-Master DMA in Video Miniport Drivers</a> for information about packet-based and common-buffer DMA transfers.



