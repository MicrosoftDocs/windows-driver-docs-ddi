---
UID: NF:video.VideoPortWritePortBufferUshort
title: VideoPortWritePortBufferUshort function (video.h)
description: The VideoPortWritePortBufferUshort function writes a number of USHORT values to a mapped I/O port.
old-location: display\videoportwriteportbufferushort.htm
tech.root: display
ms.assetid: d9be3108-27fe-4899-bf23-0f51d9309888
ms.date: 05/10/2018
keywords: ["VideoPortWritePortBufferUshort function"]
ms.keywords: VideoPortWritePortBufferUshort, VideoPortWritePortBufferUshort function [Display Devices], VideoPort_Functions_cf88884e-2891-4e82-b7e0-afaa605a2d65.xml, display.videoportwriteportbufferushort, video/VideoPortWritePortBufferUshort
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
 - VideoPortWritePortBufferUshort
 - video/VideoPortWritePortBufferUshort
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortWritePortBufferUshort
---

# VideoPortWritePortBufferUshort function


## -description

The <b>VideoPortWritePortBufferUshort</b> function writes a number of USHORT values to a mapped I/O port.

## -parameters

### -param Port

Pointer to the port. The given <i>Port</i> must be in a mapped I/O-space range returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>.

### -param Buffer 

[in]
Pointer to a buffer containing the USHORT values to be written.

### -param Count

Specifies the number of USHORT values to be transferred to the adapter.

## -returns

None

## -remarks

A miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortWritePortBufferUshort</b>.

Callers of <b>VideoPortWritePortBufferUshort</b> can be running at any IRQL, provided that the memory pointed to by the <i>Buffer</i> parameter is resident and that pointed to by the <i>Port</i> parameter is resident, mapped device memory.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>

