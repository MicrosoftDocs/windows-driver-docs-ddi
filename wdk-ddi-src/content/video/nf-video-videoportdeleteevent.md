---
UID: NF:video.VideoPortDeleteEvent
title: VideoPortDeleteEvent function (video.h)
description: The VideoPortDeleteEvent function deletes the specified event object.
old-location: display\videoportdeleteevent.htm
tech.root: display
ms.assetid: 0952f6ab-6d57-4ded-b167-74a7ace47961
ms.date: 05/10/2018
ms.keywords: VideoPortDeleteEvent, VideoPortDeleteEvent function [Display Devices], VideoPort_Functions_66e14d53-8a5e-4322-8576-4ac06230db31.xml, display.videoportdeleteevent, video/VideoPortDeleteEvent
ms.topic: function
f1_keywords:
 - "video/VideoPortDeleteEvent"
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
- VideoPortDeleteEvent
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortDeleteEvent function


## -description


The <b>VideoPortDeleteEvent</b> function deletes the specified event object.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param pEvent [in]

Pointer to the event object to be deleted.


## -returns



<b>VideoPortDeleteEvent</b> returns NO_ERROR if the event object is successfully deleted.




## -remarks



This function should not be used to delete a mapped user event. To delete a mapped user event, use <a href="https://docs.microsoft.com/windows/desktop/api/winddi/nf-winddi-engunmapevent">EngUnmapEvent</a>. 




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/winddi/nf-winddi-engunmapevent">EngUnmapEvent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportcreateevent">VideoPortCreateEvent</a>
 

 

