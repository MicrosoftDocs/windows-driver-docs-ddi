---
UID: NF:video.VideoPortReadStateEvent
title: VideoPortReadStateEvent function
description: The VideoPortReadStateEvent function returns the current state of a given event object:\_signaled or nonsignaled.
old-location: display\videoportreadstateevent.htm
tech.root: display
ms.assetid: b09787b3-aede-4e53-9e22-0e81cf2dadb1
ms.date: 05/10/2018
ms.keywords: VideoPortReadStateEvent, VideoPortReadStateEvent function [Display Devices], VideoPort_Functions_8cd6da91-d349-4ef7-b61c-2e9a22c5f25e.xml, display.videoportreadstateevent, video/VideoPortReadStateEvent
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortReadStateEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortReadStateEvent function


## -description


The <b>VideoPortReadStateEvent</b> function returns the current state of a given event object: signaled or nonsignaled.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param pEvent [in]

Pointer to the event object whose state is to be read.


## -returns



<b>VideoPortReadStateEvent</b> returns a nonzero value if the event object is currently in the signaled state. If the event object is in the nonsignaled state, this function returns zero.




## -remarks



This function is available in Windows XP and later. 



