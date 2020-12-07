---
UID: NF:video.VideoPortWritePortUlong
title: VideoPortWritePortUlong function (video.h)
description: The VideoPortWritePortUlong function writes a ULONG value to a mapped I/O port.
old-location: display\videoportwriteportulong.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["VideoPortWritePortUlong function"]
ms.keywords: VideoPortWritePortUlong, VideoPortWritePortUlong function [Display Devices], VideoPort_Functions_83cb0bbd-0dba-4cd6-b9f5-b8b0091371cd.xml, display.videoportwriteportulong, video/VideoPortWritePortUlong
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
 - VideoPortWritePortUlong
 - video/VideoPortWritePortUlong
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortWritePortUlong
---

# VideoPortWritePortUlong function


## -description

The <b>VideoPortWritePortUlong</b> function writes a ULONG value to a mapped I/O port.

## -parameters

### -param Port

Pointer to the port. The given <i>Port</i> must be in a mapped I/O-space range returned by <a href="/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>.

### -param Value

Specifies a ULONG value to be transferred to the adapter.

## -returns

None

## -remarks

A miniport driver's <a href="/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a> or <a href="/windows-hardware/drivers/ddi/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortWritePortUlong</b>.

Callers of <b>VideoPortWritePortUlong</b> can be running at any IRQL, provided that the memory pointed to by the <i>Port</i> parameter is resident, mapped device memory.

## -see-also

<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>
