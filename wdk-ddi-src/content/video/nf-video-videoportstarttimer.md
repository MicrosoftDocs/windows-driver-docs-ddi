---
UID: NF:video.VideoPortStartTimer
title: VideoPortStartTimer function (video.h)
description: The VideoPortStartTimer function enables calls to a miniport driver's HwVidTimer function.
old-location: display\videoportstarttimer.htm
tech.root: display
ms.assetid: d06ae137-d7e8-4e17-82fb-37e5c5e8ad1e
ms.date: 05/10/2018
keywords: ["VideoPortStartTimer function"]
ms.keywords: VideoPortStartTimer, VideoPortStartTimer function [Display Devices], VideoPort_Functions_1efc50e1-c79e-4ee2-acdf-35cdea97a3b9.xml, display.videoportstarttimer, video/VideoPortStartTimer
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
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - VideoPortStartTimer
 - video/VideoPortStartTimer
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortStartTimer
---

# VideoPortStartTimer function


## -description

The <b>VideoPortStartTimer</b> function enables calls to a miniport driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_timer">HwVidTimer</a> function.

## -parameters

### -param HwDeviceExtension

Pointer to the miniport driver's device extension. This pointer is the input parameter to the <i>HwVidTimer</i> function.

## -returns

None

## -remarks

After a miniport driver calls <b>VideoPortStartTimer</b>, its <i>HwVidTimer</i> function is called at approximately one-second intervals until the miniport driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportstoptimer">VideoPortStopTimer</a>. A miniport driver's <i>HwVidTimer</i> function <i>must not</i> call <b>VideoPortStopTimer</b>.

A miniport driver cannot call <b>VideoPortStartTimer</b> or <b>VideoPortStopTimer</b> if its <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> function set the <b>HwTimer</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_hw_initialization_data">VIDEO_HW_INITIALIZATION_DATA</a> structure to <b>NULL</b>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/display/driverentry-of-video-miniport-driver">DriverEntry of Video Miniport Driver</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_timer">HwVidTimer</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/ns-video-_video_hw_initialization_data">VIDEO_HW_INITIALIZATION_DATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportstoptimer">VideoPortStopTimer</a>

