---
UID: NF:video.VideoPortLogError
title: VideoPortLogError function
author: windows-driver-content
description: The VideoPortLogError function logs errors to the system event log when a miniport driver detects a hardware error condition during I/O operations.
old-location: display\videoportlogerror.htm
old-project: display
ms.assetid: d013aeb9-43a9-460f-a670-5b7bc9d3753d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: VideoPortLogError
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
req.alt-api: VideoPortLogError
req.alt-loc: Videoprt.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: <= DIRQL
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortLogError function



## -description
The <b>VideoPortLogError</b> function logs errors to the system event log when a miniport driver detects a hardware error condition during I/O operations.



## -syntax

````
VOID VideoPortLogError(
   PVOID                 HwDeviceExtension,
   PVIDEO_REQUEST_PACKET Vrp,
   VP_STATUS             ErrorCode,
   ULONG                 UniqueId
);
````


## -parameters

### -param HwDeviceExtension 

Pointer to the miniport driver's device extension.


### -param Vrp [optional]

Pointer to the video request packet (<a href="wdkgloss.v#wdkgloss.video_request_packet__vrp_#wdkgloss.video_request_packet__vrp_"><i>VRP</i></a>) if one is associated with the error; otherwise <b>NULL</b>.


### -param ErrorCode 

Specifies a miniport driver-defined error code that indicates the type of hardware error.


### -param UniqueId 

Specifies a unique identifier for the error. This value differentiates the current error from other errors with the same <i>ErrorCode</i>. For some miniport drivers, this identifies the line of code where the error was detected; for others, it is a value returned by the hardware.


## -returns
None


## -remarks
Miniport drivers should call <b>VideoPortLogError</b> to notify the user if the driver encounters unusual hardware errors during normal operations. Posting such errors to the system event log warns the user that the video adapter might be failing so the user can replace (or reconfigure) the adapter before a total hardware failure occurs.

However, miniport drivers should <i>not</i> log errors, such as "failed to detect hardware," that occur frequently during normal operation.

<b>VideoPortLogError</b> can be called from a miniport driver's <a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a> or <a href="..\video\nc-video-pminiport_synchronize_routine.md">HwVidSynchronizeExecutionCallback</a> function. 


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff570170">VideoDebugPrint</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortLogError function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

