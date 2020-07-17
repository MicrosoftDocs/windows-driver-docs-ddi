---
UID: NF:video.VideoPortQueueDpc
title: VideoPortQueueDpc function (video.h)
description: The VideoPortQueueDpc function allows a miniport driver to queue a DPC.
old-location: display\videoportqueuedpc.htm
tech.root: display
ms.assetid: 9715ff37-397b-4102-a363-443b8076f881
ms.date: 05/10/2018
keywords: ["VideoPortQueueDpc function"]
ms.keywords: VideoPortQueueDpc, VideoPortQueueDpc function [Display Devices], VideoPort_Functions_133e8c8b-e445-4f83-ad93-7eb560047f3f.xml, display.videoportqueuedpc, video/VideoPortQueueDpc
f1_keywords:
 - "video/VideoPortQueueDpc"
 - "VideoPortQueueDpc"
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
req.irql: Greater than or equal to DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Videoprt.sys
api_name:
- VideoPortQueueDpc
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortQueueDpc function


## -description


The <b>VideoPortQueueDpc</b> function allows a miniport driver to queue a DPC.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param CallbackRoutine [in]

Pointer to the miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pminiport_dpc_routine">HwVidDpcRoutine</a> to be called when the DPC is scheduled. The callback routine must be nonpaged.


### -param Context [in]

Pointer to the miniport driver-supplied context that will be passed to <i>CallbackRoutine</i>.


## -returns



<b>VideoPortQueueDpc</b> returns <b>TRUE</b> if the DPC is successfully queued, and <b>FALSE</b> otherwise.




## -remarks



The deferred procedure is run when the IRQL on the current processor drops below DISPATCH_LEVEL. Callers of <b>VideoPortQueueDpc</b> must be running at IRQL >= DISPATCH_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pminiport_dpc_routine">HwVidDpcRoutine</a>
 

 

