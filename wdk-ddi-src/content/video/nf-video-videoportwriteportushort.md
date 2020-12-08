---
UID: NF:video.VideoPortWritePortUshort
title: VideoPortWritePortUshort function (video.h)
description: The VideoPortWritePortUshort function writes a USHORT value to a mapped I/O port.
old-location: display\videoportwriteportushort.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["VideoPortWritePortUshort function"]
ms.keywords: VideoPortWritePortUshort, VideoPortWritePortUshort function [Display Devices], VideoPort_Functions_919dd8ab-f319-4071-b375-b269823adb31.xml, display.videoportwriteportushort, video/VideoPortWritePortUshort
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
 - VideoPortWritePortUshort
 - video/VideoPortWritePortUshort
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortWritePortUshort
---

# VideoPortWritePortUshort function


## -description

The <b>VideoPortWritePortUshort</b> function writes a USHORT value to a mapped I/O port.

## -parameters

### -param Port

Pointer to the port. The given <i>Port</i> must be in a mapped I/O-space range returned by <a href="/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>.

### -param Value

Specifies a USHORT value to be transferred to the adapter.

## -returns

None

## -remarks

A miniport driver's <a href="/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a> or <a href="/windows-hardware/drivers/ddi/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortWritePortUshort</b>.

Callers of <b>VideoPortWritePortUshort</b> can be running at any IRQL, provided that the memory pointed to by the <i>Port</i> parameter is resident, mapped device memory.

## -see-also

<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>
