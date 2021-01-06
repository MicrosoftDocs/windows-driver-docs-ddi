---
UID: NF:video.VideoPortCreateEvent
title: VideoPortCreateEvent function (video.h)
description: The VideoPortCreateEvent function creates an event object.
old-location: display\videoportcreateevent.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["VideoPortCreateEvent function"]
ms.keywords: VideoPortCreateEvent, VideoPortCreateEvent function [Display Devices], VideoPort_Functions_29412925-5117-4759-b4ea-b4adb4358a8c.xml, display.videoportcreateevent, video/VideoPortCreateEvent
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - VideoPortCreateEvent
 - video/VideoPortCreateEvent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortCreateEvent
---

# VideoPortCreateEvent function


## -description

The <b>VideoPortCreateEvent</b> function creates an event object.

## -parameters

### -param HwDeviceExtension 

[in]
Pointer to the miniport driver's device extension.

### -param EventFlag 

[in]
Specifies the event type and initial event state. This can be an ORed combination of the following flags:

|Flag|Meaning|
|--- |--- |
|INITIAL_EVENT_SIGNALED|Set this flag to indicate the signaled state for the event object. Otherwise, the initial state of the event is nonsignaled.|
|NOTIFICATION_EVENT|Set this flag to create a notification event. If this flag is not set, a synchronization event is created.|

### -param Unused 

[in]
Is currently ignored by the video port driver and must be set to <b>NULL</b>.

### -param ppEvent 

[out]
Pointer to the memory location at which a pointer to the event object will be returned.

## -returns

<b>VideoPortCreateEvent</b> returns NO_ERROR if the event object is successfully created.

## -remarks

When a synchronization event is set to the signaled state, a single thread that was waiting for the signaled state is released (its dispatch state transitions from waiting to ready, standby, or running), and the event is automatically reset to the nonsignaled state.

When a notification event is set to the signaled state, all threads that were waiting for the signaled state are released, and the event remains in the signaled state until it is explicitly reset to the nonsignaled state.

## -see-also

<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportdeleteevent">VideoPortDeleteEvent</a>
