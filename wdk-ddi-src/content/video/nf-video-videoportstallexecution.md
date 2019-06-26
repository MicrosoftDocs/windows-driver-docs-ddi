---
UID: NF:video.VideoPortStallExecution
title: VideoPortStallExecution function (video.h)
description: The VideoPortStallExecution function retains control of the processor for the specified number of microseconds and returns to the caller.
old-location: display\videoportstallexecution.htm
tech.root: display
ms.assetid: 70b406f8-d9ac-4882-89bc-e257cbe06921
ms.date: 05/10/2018
ms.keywords: VideoPortStallExecution, VideoPortStallExecution function [Display Devices], VideoPort_Functions_bda7e25d-a636-4ceb-ae47-c74435f9483a.xml, display.videoportstallexecution, video/VideoPortStallExecution
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
req.irql: Any level
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Videoprt.sys
api_name:
- VideoPortStallExecution
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortStallExecution function


## -description


The <b>VideoPortStallExecution</b> function retains control of the processor for the specified number of microseconds and returns to the caller.


## -parameters




### -param Microseconds

Specifies the delay interval, in microseconds.


## -returns



None




## -remarks



Maximum acceptable values for <i>Microseconds</i> are thousands of microseconds during miniport driver initialization. Otherwise, the given delay interval must be no more than 50 microseconds. In general, <b>VideoPortStallExecution</b> can be called only if the miniport driver must wait for a very few microseconds for its adapter to update state.

While a miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortStallExecution</b>, the miniport driver should be designed to avoid such a call if at all possible. Delays while running at high hardware priorities adversely affect the overall I/O throughput of the system and can freeze the machine.

If a miniport driver has work to be done at regular intervals of more than 50 microseconds, it should implement the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pvideo_hw_timer">HwVidTimer</a> function. Calls to a miniport driver-supplied <i>HwVidTimer</i> function at approximately one-second intervals can be enabled with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportstarttimer">VideoPortStartTimer</a> and disabled with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportstoptimer">VideoPortStopTimer</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pvideo_hw_timer">HwVidTimer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportstarttimer">VideoPortStartTimer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportstoptimer">VideoPortStopTimer</a>
 

 

