---
UID: NF:video.VideoPortEnableInterrupt
title: VideoPortEnableInterrupt function
author: windows-driver-content
description: The VideoPortEnableInterrupt function is obsolete and should not be called.The VideoPortEnableInterrupt function reenables interrupts from a video adapter after a call to VideoPortDisableInterrupt.
old-location: display\videoportenableinterrupt.htm
old-project: display
ms.assetid: d40b0bc6-fad0-4c83-b1ca-c5105112ae2d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: VideoPortEnableInterrupt, VideoPortEnableInterrupt function [Display Devices], VideoPort_Functions_63966cab-5451-4fa0-ae8f-635fae20aabd.xml, display.videoportenableinterrupt, video/VideoPortEnableInterrupt
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortEnableInterrupt
product:
- Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortEnableInterrupt function


## -description


The <b>VideoPortEnableInterrupt</b> function is <b>obsolete</b> and should not be called.

The <b>VideoPortEnableInterrupt</b> function reenables interrupts from a video adapter after a call to <b>VideoPortDisableInterrupt</b>.


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's device extension.


## -returns



If <b>VideoPortEnableInterrupt</b> succeeds, it returns NO_ERROR. Otherwise, it returns ERROR_INVALID_FUNCTION.




## -remarks



If you need to disable interrupts for the display adapter, write hardware-specific code to prevent the display adapter from generating interrupts. To subsequently enable interrupts, write hardware-specific code to allow the display adapter to resume generating interrupts.

You should not call <a href="https://msdn.microsoft.com/library/windows/hardware/ff570294">VideoPortDisableInterrupt</a> or <b>VideoPortEnableInterrupt</b> for the following reasons:

<ul>
<li>
Can disable interrupts for other devices that share an interrupt vector with the display adapter.

</li>
<li>
Disables interrupts only on the processor where the current thread is running. On a multiprocessor computer, the display adapter can still interrupt another processor.

</li>
<li>
On a multiprocessor machine, a call to <b>VideoPortEnableInterrupt</b> might run on a different processor than the previous corresponding call to <b>VideoPortDisableInterrupt</b>. In that case, interrupts will remain disabled for the processor on which <b>VideoPortDisableInterrupt</b> ran.

</li>
</ul>
If the video miniport driver has not registered an <a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a> routine for the display adapter, <b>VideoPortEnableInterrupt</b> returns ERROR_INVALID_FUNCTION. 




## -see-also




<a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a>



<a href="https://msdn.microsoft.com/04e3bac6-c905-4c95-bd1b-e85b46c4296d">HwVidSynchronizeExecutionCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570505">VIDEO_HW_INITIALIZATION_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570294">VideoPortDisableInterrupt</a>
 

 

