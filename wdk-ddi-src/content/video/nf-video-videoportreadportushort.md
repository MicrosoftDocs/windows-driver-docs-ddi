---
UID: NF:video.VideoPortReadPortUshort
title: VideoPortReadPortUshort function (video.h)
description: The VideoPortReadPortUshort function reads a USHORT value from a mapped I/O port.
old-location: display\videoportreadportushort.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["VideoPortReadPortUshort function"]
ms.keywords: VideoPortReadPortUshort, VideoPortReadPortUshort function [Display Devices], VideoPort_Functions_cb14aa82-3092-4982-83c5-4682d7a487c0.xml, display.videoportreadportushort, video/VideoPortReadPortUshort
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
 - VideoPortReadPortUshort
 - video/VideoPortReadPortUshort
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortReadPortUshort
---

# VideoPortReadPortUshort function


## -description

The <b>VideoPortReadPortUshort</b> function reads a USHORT value from a mapped I/O port.

## -parameters

### -param Port

Pointer to the port. The given <i>Port</i> must be in a mapped I/O-space range returned by <a href="/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>.

## -returns

<b>VideoPortReadPortUshort</b> returns the USHORT value read from the adapter.

## -remarks

A miniport driver's <a href="/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a> or <a href="/windows-hardware/drivers/ddi/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortReadPortUshort</b>.

Callers of <b>VideoPortReadPortUshort</b> can be running at any IRQL, provided that the memory pointed to by the <i>Port</i> parameter is resident, mapped device memory.

## -see-also

<a href="/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a>



<a href="/windows-hardware/drivers/ddi/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a>



<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>
