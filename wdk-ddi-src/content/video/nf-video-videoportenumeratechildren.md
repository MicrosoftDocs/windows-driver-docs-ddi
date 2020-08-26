---
UID: NF:video.VideoPortEnumerateChildren
title: VideoPortEnumerateChildren function (video.h)
description: The VideoPortEnumerateChildren function allows a video miniport driver to force a reenumeration of its child devices.
old-location: display\videoportenumeratechildren.htm
tech.root: display
ms.assetid: 41f081f3-4079-46f8-9d22-76a2d9e992b5
ms.date: 05/10/2018
keywords: ["VideoPortEnumerateChildren function"]
ms.keywords: VideoPortEnumerateChildren, VideoPortEnumerateChildren function [Display Devices], VideoPort_Functions_8bc790f2-319f-41a6-9bf7-02a8605d2cc1.xml, display.videoportenumeratechildren, video/VideoPortEnumerateChildren
f1_keywords:
 - "video/VideoPortEnumerateChildren"
 - "VideoPortEnumerateChildren"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Videoprt.sys
api_name:
- VideoPortEnumerateChildren
targetos: Windows
req.typenames: 
---

# VideoPortEnumerateChildren function


## -description


The <b>VideoPortEnumerateChildren</b> function allows a video miniport driver to force a reenumeration of its child devices.


## -parameters




### -param HwDeviceExtension 
[in]
Pointer to the miniport driver's device extension.


### -param Reserved 
[in]
Must be set to <b>NULL</b>.


## -returns



<b>VideoPortEnumerateChildren</b> returns NO_ERROR.




## -remarks



Some devices generate an interrupt when new hardware is connected to the system, or when existing hardware is disconnected from the system. For these devices, <b>VideoPortEnumerateChildren</b> can make such system changes as seamless as possible. The following is one possible scenario that forces the reenumeration of child devices through <b>VideoPortEnumerateChildren</b>:

<ul>
<li>
New hardware is connected, which generates an interrupt.

</li>
<li>
The miniport driver's interrupt handler (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a>) queues a DPC routine (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pminiport_dpc_routine">HwVidDpcRoutine</a>) by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportqueuedpc">VideoPortQueueDpc</a>.

</li>
<li>
The asynchronously executed DPC contains a call to <b>VideoPortEnumerateChildren</b>.

</li>
</ul>
<b>VideoPortEnumerateChildren</b> causes <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_get_child_descriptor">HwVidGetVideoChildDescriptor</a> to be called, allowing the Plug and Play Manager to enumerate all of the adapter's child devices.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pminiport_dpc_routine">HwVidDpcRoutine</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_get_child_descriptor">HwVidGetVideoChildDescriptor</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_interrupt">HwVidInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportqueuedpc">VideoPortQueueDpc</a>
 

 

