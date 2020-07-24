---
UID: NF:video.VideoPortUnmapDmaMemory
title: VideoPortUnmapDmaMemory function (video.h)
description: The VideoPortUnmapDmaMemory function is obsolete in Windows 2000 and later.VideoPortUnmapDmaMemory unmaps a range of memory previously mapped by VideoPortMapDmaMemory.
old-location: display\videoportunmapdmamemory.htm
tech.root: display
ms.assetid: f3d05263-5e6b-4875-afff-1166928778db
ms.date: 05/10/2018
keywords: ["VideoPortUnmapDmaMemory function"]
ms.keywords: VideoPortUnmapDmaMemory, VideoPortUnmapDmaMemory function [Display Devices], VideoPort_Functions_f2162fff-c7a8-4dde-aa17-94377f0cf716.xml, display.videoportunmapdmamemory, video/VideoPortUnmapDmaMemory
f1_keywords:
 - "video/VideoPortUnmapDmaMemory"
 - "VideoPortUnmapDmaMemory"
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
- VideoPortUnmapDmaMemory
targetos: Windows
req.typenames: 
---

# VideoPortUnmapDmaMemory function


## -description


The <b>VideoPortUnmapDmaMemory</b> function is <b>obsolete</b> in Windows 2000 and later.

<b>VideoPortUnmapDmaMemory</b> unmaps a range of memory previously mapped by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportmapdmamemory">VideoPortMapDmaMemory</a>.


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's device extension.


### -param VirtualAddress

Pointer to a virtual address within the mapped range to be released.


### -param ProcessHandle

Is the handle to the current process.


### -param BoardMemoryHandle

Is the handle to adapter's memory.


## -returns



<b>VideoPortUnmapDmaMemory</b> always <b>FALSE</b>.




## -remarks



See <a href="https://docs.microsoft.com/windows-hardware/drivers/display/bus-master-dma-in-video-miniport-drivers">Bus-Master DMA in Video Miniport Drivers</a> for information about packet-based and common-buffer DMA transfers.



