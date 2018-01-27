---
UID: NF:video.VideoPortClearEvent
title: VideoPortClearEvent function
author: windows-driver-content
description: The VideoPortClearEvent function sets a given event object to the nonsignaled state.
old-location: display\videoportclearevent.htm
old-project: display
ms.assetid: 70b9b8b4-8adc-4628-a37b-b513ecaca9ca
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: VideoPortClearEvent, VideoPortClearEvent function [Display Devices], VideoPort_Functions_4b6d9a3c-ee76-4c45-888f-4ef37f802e6b.xml, video/VideoPortClearEvent, display.videoportclearevent
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows XP and later versions of the Windows operating systems.
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	DllExport
apilocation: 
-	Videoprt.sys
apiname: 
-	VideoPortClearEvent
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortClearEvent function


## -description


The <b>VideoPortClearEvent</b> function sets a given event object to the nonsignaled state.


## -syntax


````
VOID VideoPortClearEvent(
  _In_ PVOID  HwDeviceExtension,
  _In_ PEVENT pEvent
);
````


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param pEvent [in]

Pointer to the event object.


## -returns


None



## -remarks


To set the state of an event object to the signaled state, use <a href="..\video\nf-video-videoportsetevent.md">VideoPortSetEvent</a>. 



## -see-also

<a href="..\video\nf-video-videoportsetevent.md">VideoPortSetEvent</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortClearEvent function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

