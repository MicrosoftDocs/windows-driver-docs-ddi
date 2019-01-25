---
UID: NF:video.VideoPortLogError
title: VideoPortLogError function (video.h)
description: The VideoPortLogError function logs errors to the system event log when a miniport driver detects a hardware error condition during I/O operations.
old-location: display\videoportlogerror.htm
tech.root: display
ms.assetid: d013aeb9-43a9-460f-a670-5b7bc9d3753d
ms.date: 05/10/2018
ms.keywords: VideoPortLogError, VideoPortLogError function [Display Devices], VideoPort_Functions_18666bd9-b871-4e4c-9f31-bd5cbd505d52.xml, display.videoportlogerror, video/VideoPortLogError
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
req.irql: "<= DIRQL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortLogError
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortLogError function


## -description


The <b>VideoPortLogError</b> function logs errors to the system event log when a miniport driver detects a hardware error condition during I/O operations.


## -parameters




### -param HwDeviceExtension

Pointer to the miniport driver's device extension.


### -param OPTIONAL

*Vrp* [optional]

<p>Pointer to the video request packet (<a href="wdkgloss.v#wdkgloss.video_request_packet__vrp_#wdkgloss.video_request_packet__vrp_"><i>VRP</i></a>) if one is associated with the error; otherwise <b>NULL</b>.</p>


### -param ErrorCode

Specifies a miniport driver-defined error code that indicates the type of hardware error.


### -param UniqueId

Specifies a unique identifier for the error. This value differentiates the current error from other errors with the same <i>ErrorCode</i>. For some miniport drivers, this identifies the line of code where the error was detected; for others, it is a value returned by the hardware.


## -returns



None




## -remarks



Miniport drivers should call <b>VideoPortLogError</b> to notify the user if the driver encounters unusual hardware errors during normal operations. Posting such errors to the system event log warns the user that the video adapter might be failing so the user can replace (or reconfigure) the adapter before a total hardware failure occurs.

However, miniport drivers should <i>not</i> log errors, such as "failed to detect hardware," that occur frequently during normal operation.

<b>VideoPortLogError</b> can be called from a miniport driver's <a href="https://msdn.microsoft.com/523471e3-cf1e-48d2-b5f0-2f8d19ad71e0">HwVidInterrupt</a> or <a href="https://msdn.microsoft.com/04e3bac6-c905-4c95-bd1b-e85b46c4296d">HwVidSynchronizeExecutionCallback</a> function. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570170">VideoDebugPrint</a>
 

 

