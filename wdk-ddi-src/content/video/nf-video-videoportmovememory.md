---
UID: NF:video.VideoPortMoveMemory
title: VideoPortMoveMemory function (video.h)
description: The VideoPortMoveMemory function copies data from the source location to the destination location in system memory.
old-location: display\videoportmovememory.htm
tech.root: display
ms.assetid: 32b754ef-2a85-4ba7-9d4f-3c2de2501319
ms.date: 05/10/2018
keywords: ["VideoPortMoveMemory function"]
ms.keywords: VideoPortMoveMemory, VideoPortMoveMemory function [Display Devices], VideoPort_Functions_ab574585-85be-48ea-9713-25867812699a.xml, display.videoportmovememory, video/VideoPortMoveMemory
f1_keywords:
 - "video/VideoPortMoveMemory"
 - "VideoPortMoveMemory"
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
req.irql: See Remarks section.
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Videoprt.sys
api_name:
- VideoPortMoveMemory
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortMoveMemory function


## -description


The <b>VideoPortMoveMemory</b> function copies data from the source location to the destination location in system memory.


## -parameters




### -param Destination [in, out]

Pointer to the destination location.


### -param Source [in, out]

Pointer to the location of the data to copy.


### -param Length

Specifies the number of bytes to copy.


## -returns



None




## -remarks



<b>VideoPortMoveMemory</b> moves memory either forward or backward, aligned or unaligned, in 4-byte blocks, followed by any remaining bytes.

The given <i>Destination</i> and <i>Source</i> must be in a mapped logical range returned by <b>VideoPortGetDeviceBase</b> and/or a <a href="https://docs.microsoft.com/windows-hardware/drivers/">system space</a> RAM address, such as an address on the stack.

Callers of <b>VideoPortMoveMemory</b> can be running at any IRQL if both memory blocks are resident. Otherwise, the caller must be running at IRQL < DISPATCH_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportcomparememory">VideoPortCompareMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportzerodevicememory">VideoPortZeroDeviceMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportzeromemory">VideoPortZeroMemory</a>
 

 

