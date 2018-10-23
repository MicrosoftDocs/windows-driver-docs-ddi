---
UID: NF:video.VideoPortStartTimer
title: VideoPortStartTimer function
author: windows-driver-content
description: The VideoPortStartTimer function enables calls to a miniport driver's HwVidTimer function.
old-location: display\videoportstarttimer.htm
tech.root: display
ms.assetid: d06ae137-d7e8-4e17-82fb-37e5c5e8ad1e
ms.date: 05/10/2018
ms.keywords: VideoPortStartTimer, VideoPortStartTimer function [Display Devices], VideoPort_Functions_1efc50e1-c79e-4ee2-acdf-35cdea97a3b9.xml, display.videoportstarttimer, video/VideoPortStartTimer
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortStartTimer
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortStartTimer function


## -description


The <b>VideoPortStartTimer</b> function enables calls to a miniport driver's <a href="https://msdn.microsoft.com/bd41bbbf-4ec8-4e6c-8620-d8a9fe0b8bad">HwVidTimer</a> function.


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's device extension. This pointer is the input parameter to the <i>HwVidTimer</i> function.


## -returns



None




## -remarks



After a miniport driver calls <b>VideoPortStartTimer</b>, its <i>HwVidTimer</i> function is called at approximately one-second intervals until the miniport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff570371">VideoPortStopTimer</a>. A miniport driver's <i>HwVidTimer</i> function <i>must not</i> call <b>VideoPortStopTimer</b>.

A miniport driver cannot call <b>VideoPortStartTimer</b> or <b>VideoPortStopTimer</b> if its <a href="https://msdn.microsoft.com/library/windows/hardware/ff552644">DriverEntry</a> function set the <b>HwTimer</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff570505">VIDEO_HW_INITIALIZATION_DATA</a> structure to <b>NULL</b>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556159">DriverEntry of Video Miniport Driver</a>



<a href="https://msdn.microsoft.com/bd41bbbf-4ec8-4e6c-8620-d8a9fe0b8bad">HwVidTimer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570505">VIDEO_HW_INITIALIZATION_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570371">VideoPortStopTimer</a>
 

 

