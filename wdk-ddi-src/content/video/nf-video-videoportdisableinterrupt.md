---
UID: NF:video.VideoPortDisableInterrupt
title: VideoPortDisableInterrupt function (video.h)
description: The VideoPortDisableInterrupt function is obsolete and should not be called.The VideoPortDisableInterrupt function disables interrupts from a video adapter.
old-location: display\videoportdisableinterrupt.htm
tech.root: display
ms.assetid: 4a2be8af-e393-4c7f-9377-cb2842778104
ms.date: 05/10/2018
keywords: ["VideoPortDisableInterrupt function"]
ms.keywords: VideoPortDisableInterrupt, VideoPortDisableInterrupt function [Display Devices], VideoPort_Functions_b01a5ae8-7e44-4ac8-9e11-ee266f34a4da.xml, display.videoportdisableinterrupt, video/VideoPortDisableInterrupt
f1_keywords:
 - "video/VideoPortDisableInterrupt"
 - "VideoPortDisableInterrupt"
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
- VideoPortDisableInterrupt
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortDisableInterrupt function


## -description


The <b>VideoPortDisableInterrupt</b> function is <b>obsolete</b> and should not be called.

The <b>VideoPortDisableInterrupt</b> function disables interrupts from a video adapter. As a result, interrupts coming from the device are ignored by the operating system and are not forwarded to the driver.


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's device extension.


## -returns



If <b>VideoPortDisableInterrupt</b> succeeds, it returns NO_ERROR. Otherwise, it returns ERROR_INVALID_FUNCTION.




## -remarks



If you need to disable interrupts for the display adapter, write hardware-specific code to prevent the display adapter from generating interrupts. To subsequently enable interrupts, write hardware-specific code to allow the display adapter to resume generating interrupts.

You should not call <b>VideoPortDisableInterrupt</b> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportenableinterrupt">VideoPortEnableInterrupt</a> for the following reasons:

<ul>
<li>
Can disable interrupts for other devices that share an interrupt vector with the display adapter.

</li>
<li>
Disables interrupts only on the processor where the current thread is running. On a multiprocessor computer, the display adapter can still interrupt another processor.

</li>
<li>
On a multiprocessor computer, a call to <b>VideoPortEnableInterrupt</b> might run on a different processor than the previous corresponding call to <b>VideoPortDisableInterrupt</b>. In that case, interrupts will remain disabled for the processor on which <b>VideoPortDisableInterrupt</b> ran.

</li>
</ul>
If the video miniport driver has not registered an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a> routine for the display adapter, <b>VideoPortDisableInterrupt</b> returns ERROR_INVALID_FUNCTION. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pminiport_synchronize_routine">HwVidSynchronizeExecutionCallback</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_hw_initialization_data">VIDEO_HW_INITIALIZATION_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportenableinterrupt">VideoPortEnableInterrupt</a>
 

 

