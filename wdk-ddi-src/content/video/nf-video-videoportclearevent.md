---
UID: NF:video.VideoPortClearEvent
title: VideoPortClearEvent function (video.h)
description: The VideoPortClearEvent function sets a given event object to the nonsignaled state.
old-location: display\videoportclearevent.htm
tech.root: display
ms.assetid: 70b9b8b4-8adc-4628-a37b-b513ecaca9ca
ms.date: 05/10/2018
ms.keywords: VideoPortClearEvent, VideoPortClearEvent function [Display Devices], VideoPort_Functions_4b6d9a3c-ee76-4c45-888f-4ef37f802e6b.xml, display.videoportclearevent, video/VideoPortClearEvent
ms.topic: function
f1_keywords:
 - "video/VideoPortClearEvent"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Videoprt.sys
api_name:
- VideoPortClearEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortClearEvent function


## -description


The <b>VideoPortClearEvent</b> function sets a given event object to the nonsignaled state.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param pEvent [in]

Pointer to the event object.


## -returns



None




## -remarks



To set the state of an event object to the signaled state, use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportsetevent">VideoPortSetEvent</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportsetevent">VideoPortSetEvent</a>
 

 

