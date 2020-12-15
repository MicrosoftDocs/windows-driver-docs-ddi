---
UID: NF:video.VideoPortReadPortBufferUchar
title: VideoPortReadPortBufferUchar function (video.h)
description: The VideoPortReadPortBufferUchar function reads a number of bytes from a mapped I/O port and writes them into a buffer.
old-location: display\videoportreadportbufferuchar.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["VideoPortReadPortBufferUchar function"]
ms.keywords: VideoPortReadPortBufferUchar, VideoPortReadPortBufferUchar function [Display Devices], VideoPort_Functions_b3c67bc0-e12c-4625-bba6-d7fb64e0c824.xml, display.videoportreadportbufferuchar, video/VideoPortReadPortBufferUchar
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
targetos: Windows
req.typenames: 
f1_keywords:
 - VideoPortReadPortBufferUchar
 - video/VideoPortReadPortBufferUchar
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortReadPortBufferUchar
---

# VideoPortReadPortBufferUchar function


## -description

The <b>VideoPortReadPortBufferUchar</b> function reads a number of bytes from a mapped I/O port and writes them into a buffer.

## -parameters

### -param Port

Pointer to the I/O port. The given <i>Port</i> must be in a mapped I/O-space range returned by <a href="/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>.

### -param Buffer 

[out]
Pointer to a buffer into which the UCHAR values are written.

### -param Count

Specifies the number of bytes to be written to the buffer.

## -returns

None

## -remarks

The buffer must be large enough to contain at least the specified number of bytes.

A miniport driver's <a href="/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a> or <a href="/windows-hardware/drivers/ddi/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortReadPortBufferUchar</b>.

Callers of <b>VideoPortReadPortBufferUchar</b> can be running at any IRQL, provided that the memory pointed to by the <i>Buffer</i> parameter is resident and that pointed to by the <i>Port</i> parameter is resident, mapped device memory.

## -see-also

<a href="/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a>



<a href="/windows-hardware/drivers/ddi/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a>



<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>
