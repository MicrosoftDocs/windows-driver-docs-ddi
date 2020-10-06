---
UID: NF:video.VideoPortCompareMemory
title: VideoPortCompareMemory function (video.h)
description: The VideoPortCompareMemory function compares two blocks of system memory, byte-by-byte, and returns the number of compared bytes that are equivalent.
old-location: display\videoportcomparememory.htm
tech.root: display
ms.assetid: 89528b31-4d81-4612-92d7-5f64bdca8108
ms.date: 05/10/2018
keywords: ["VideoPortCompareMemory function"]
ms.keywords: VideoPortCompareMemory, VideoPortCompareMemory function [Display Devices], VideoPort_Functions_87b1236e-d77b-4930-897f-d5b33b1130aa.xml, display.videoportcomparememory, video/VideoPortCompareMemory
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
req.irql: Any level (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - VideoPortCompareMemory
 - video/VideoPortCompareMemory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortCompareMemory
---

# VideoPortCompareMemory function


## -description

The <b>VideoPortCompareMemory</b> function compares two blocks of system memory, byte-by-byte, and returns the number of compared bytes that are equivalent.

## -parameters

### -param Source1

Pointer to the first block of memory to compare.

### -param Source2

Pointer to the second block of memory to compare.

### -param Length

Specifies the number of bytes to be compared.

## -returns

<b>VideoPortCompareMemory</b> returns the number of bytes that are equivalent. If both blocks are equivalent, it returns the <i>Length</i> parameter.

## -remarks

The values in the <i>Source1</i> and <i>Source2</i> parameters must be in a mapped logical range returned by <a href="/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a> and/or a <a href="/windows-hardware/drivers/">system space</a> RAM address, such as an address on the stack.

Callers of <b>VideoPortCompareMemory</b> can be running at any IRQL if both blocks of memory are resident.

## -see-also

<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>



<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportmovememory">VideoPortMoveMemory</a>



<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportscanrom">VideoPortScanRom</a>



<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportzerodevicememory">VideoPortZeroDeviceMemory</a>



<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportzeromemory">VideoPortZeroMemory</a>