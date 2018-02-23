---
UID: NF:video.VideoPortStopTimer
title: VideoPortStopTimer function
author: windows-driver-content
description: The VideoPortStopTimer function disables calls to a miniport driver's HwVidTimer function.
old-location: display\videoportstoptimer.htm
old-project: display
ms.assetid: 8f6927e1-2342-4816-aa43-1849c3a7702b
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: display.videoportstoptimer, VideoPortStopTimer function [Display Devices], video/VideoPortStopTimer, VideoPort_Functions_335cb68f-85a0-4e57-9e91-65df281f68a4.xml, VideoPortStopTimer
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Videoprt.sys
apiname:
-	VideoPortStopTimer
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortStopTimer function


## -description


The <b>VideoPortStopTimer</b> function disables calls to a miniport driver's <a href="..\video\nc-video-pvideo_hw_timer.md">HwVidTimer</a> function.


## -syntax


````
VOID VideoPortStopTimer(
   PVOID HwDeviceExtension
);
````


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's device extension. This pointer is the input parameter to the <i>HwVidTimer</i> function.


## -returns



None




## -remarks



After a miniport driver calls <a href="..\video\nf-video-videoportstarttimer.md">VideoPortStartTimer</a>, its <i>HwVidTimer</i> function is called at approximately one-second intervals until the miniport driver calls <b>VideoPortStopTimer</b>. A miniport driver's <i>HwVidTimer</i> function <i>must not</i> call <b>VideoPortStopTimer</b>.

A miniport driver cannot call <b>VideoPortStartTimer</b> or <b>VideoPortStopTimer</b> if its <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> function set the <b>HwTimer</b> member of the <a href="..\video\ns-video-_video_hw_initialization_data.md">VIDEO_HW_INITIALIZATION_DATA</a> structure to <b>NULL</b>. 




## -see-also

<a href="..\video\nc-video-pvideo_hw_timer.md">HwVidTimer</a>



<a href="..\video\nf-video-videoportstarttimer.md">VideoPortStartTimer</a>



<a href="..\video\ns-video-_video_hw_initialization_data.md">VIDEO_HW_INITIALIZATION_DATA</a>



<a href="..\video\nc-video-pvideo_hw_timer.md">HwVidTimer</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortStopTimer function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

