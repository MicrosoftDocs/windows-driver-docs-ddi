---
UID: NF:video.VideoPortSetEvent
title: VideoPortSetEvent function (video.h)
description: The VideoPortSetEvent function sets an event object to the signaled state if it was not already in that state, and returns the event object's previous state.
old-location: display\videoportsetevent.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["VideoPortSetEvent function"]
ms.keywords: VideoPortSetEvent, VideoPortSetEvent function [Display Devices], VideoPort_Functions_8efce2e2-f5e7-402a-a5bf-03c23ac85992.xml, display.videoportsetevent, video/VideoPortSetEvent
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
targetos: Windows
req.typenames: 
f1_keywords:
 - VideoPortSetEvent
 - video/VideoPortSetEvent
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortSetEvent
---

# VideoPortSetEvent function


## -description

The <b>VideoPortSetEvent</b> function sets an event object to the signaled state if it was not already in that state, and returns the event object's previous state.

## -parameters

### -param HwDeviceExtension [in]


Pointer to the miniport driver's device extension.

### -param pEvent [in]


Pointer to the event object whose state is to be set.

## -returns

<b>VideoPortSetEvent</b> returns a nonzero value if the event object was previously in the signaled state.

## -see-also

<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportclearevent">VideoPortClearEvent</a>
