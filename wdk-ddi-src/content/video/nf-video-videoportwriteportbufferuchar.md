---
UID: NF:video.VideoPortWritePortBufferUchar
title: VideoPortWritePortBufferUchar function (video.h)
description: The VideoPortWritePortBufferUchar function writes a number of bytes to a mapped I/O port.
old-location: display\videoportwriteportbufferuchar.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["VideoPortWritePortBufferUchar function"]
ms.keywords: VideoPortWritePortBufferUchar, VideoPortWritePortBufferUchar function [Display Devices], VideoPort_Functions_c7f29624-d08d-437f-8b03-6f6f3b1f27b9.xml, display.videoportwriteportbufferuchar, video/VideoPortWritePortBufferUchar
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
 - VideoPortWritePortBufferUchar
 - video/VideoPortWritePortBufferUchar
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortWritePortBufferUchar
---

# VideoPortWritePortBufferUchar function


## -description

The <b>VideoPortWritePortBufferUchar</b> function writes a number of bytes to a mapped I/O port.

## -parameters

### -param Port

Pointer to the port. The given <i>Port</i> must be in a mapped I/O-space range returned by <a href="/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>.

### -param Buffer [in]


Pointer to a buffer containing the bytes to be written.

### -param Count

Specifies the number of bytes to be transferred to the adapter.

## -returns

None

## -remarks

A miniport driver's <a href="/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a> or <a href="/windows-hardware/drivers/ddi/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortWritePortBufferUchar</b>.

Callers of <b>VideoPortWritePortBufferUchar</b> can be running at any IRQL, provided that the memory pointed to by the <i>Buffer</i> parameter is resident and that pointed to by the <i>Port</i> parameter is resident, mapped device memory.

## -see-also

<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>
