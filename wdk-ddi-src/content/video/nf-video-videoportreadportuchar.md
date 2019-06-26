---
UID: NF:video.VideoPortReadPortUchar
title: VideoPortReadPortUchar function (video.h)
description: The VideoPortReadPortUchar function reads a byte from a mapped I/O port.
old-location: display\videoportreadportuchar.htm
tech.root: display
ms.assetid: 1cc93e46-406f-4f75-ae5d-7a4986286640
ms.date: 05/10/2018
ms.keywords: VideoPortReadPortUchar, VideoPortReadPortUchar function [Display Devices], VideoPort_Functions_128aedd7-fb7b-4e0e-8447-12733a245bc0.xml, display.videoportreadportuchar, video/VideoPortReadPortUchar
ms.topic: function
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
- VideoPortReadPortUchar
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortReadPortUchar function


## -description


The <b>VideoPortReadPortUchar</b> function reads a byte from a mapped I/O port.


## -parameters




### -param Port

Pointer to the port. The given <i>Port</i> must be in a mapped I/O-space range returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>.


## -returns



<b>VideoPortReadPortUchar</b> returns the byte read from the adapter.




## -remarks



A miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortReadPortUchar</b>.

Callers of <b>VideoPortReadPortUchar</b> can be running at any IRQL, provided that the memory pointed to by the <i>Port</i> parameter is resident, mapped device memory.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportgetdevicebase">VideoPortGetDeviceBase</a>
 

 

