---
UID: NF:video.VideoPortStopTimer
title: VideoPortStopTimer function (video.h)
description: The VideoPortStopTimer function disables calls to a miniport driver's HwVidTimer function.
old-location: display\videoportstoptimer.htm
tech.root: display
ms.assetid: 8f6927e1-2342-4816-aa43-1849c3a7702b
ms.date: 05/10/2018
ms.keywords: VideoPortStopTimer, VideoPortStopTimer function [Display Devices], VideoPort_Functions_335cb68f-85a0-4e57-9e91-65df281f68a4.xml, display.videoportstoptimer, video/VideoPortStopTimer
ms.topic: function
f1_keywords:
 - "video/VideoPortStopTimer"
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Videoprt.sys
api_name:
- VideoPortStopTimer
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortStopTimer function


## -description


The <b>VideoPortStopTimer</b> function disables calls to a miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pvideo_hw_timer">HwVidTimer</a> function.


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's device extension. This pointer is the input parameter to the <i>HwVidTimer</i> function.


## -returns



None




## -remarks



After a miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportstarttimer">VideoPortStartTimer</a>, its <i>HwVidTimer</i> function is called at approximately one-second intervals until the miniport driver calls <b>VideoPortStopTimer</b>. A miniport driver's <i>HwVidTimer</i> function <i>must not</i> call <b>VideoPortStopTimer</b>.

A miniport driver cannot call <b>VideoPortStartTimer</b> or <b>VideoPortStopTimer</b> if its <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> function set the <b>HwTimer</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/ns-video-_video_hw_initialization_data">VIDEO_HW_INITIALIZATION_DATA</a> structure to <b>NULL</b>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/display/driverentry-of-video-miniport-driver">DriverEntry of Video Miniport Driver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nc-video-pvideo_hw_timer">HwVidTimer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/ns-video-_video_hw_initialization_data">VIDEO_HW_INITIALIZATION_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/video/nf-video-videoportstarttimer">VideoPortStartTimer</a>
 

 

