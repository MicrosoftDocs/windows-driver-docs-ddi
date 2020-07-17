---
UID: NF:video.VideoPortReadPortUlong
title: VideoPortReadPortUlong function (video.h)
description: The VideoPortReadPortUlong function reads a ULONG value from a mapped I/O port.
old-location: display\videoportreadportulong.htm
tech.root: display
ms.assetid: 73402b35-85ce-4bb1-8ec5-619805d5a3e0
ms.date: 05/10/2018
keywords: ["VideoPortReadPortUlong function"]
ms.keywords: VideoPortReadPortUlong, VideoPortReadPortUlong function [Display Devices], VideoPort_Functions_347d0c32-a4b6-4061-bbd5-16325e0e3af6.xml, display.videoportreadportulong, video/VideoPortReadPortUlong
f1_keywords:
 - "video/VideoPortReadPortUlong"
 - "VideoPortReadPortUlong"
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
- VideoPortReadPortUlong
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortReadPortUlong function


## -description


The <b>VideoPortReadPortUlong</b> function reads a ULONG value from a mapped I/O port.


## -parameters




### -param Port

Pointer to the port. The given <i>Port</i> must be in a mapped I/O-space range returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>.


## -returns



<b>VideoPortReadPortUlong</b> returns the ULONG value read from the adapter.




## -remarks



A miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortReadPortUlong</b>.

Callers of <b>VideoPortReadPortUlong</b> can be running at any IRQL, provided that the memory pointed to by the <i>Port</i> parameter is resident, mapped device memory.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>
 

 

