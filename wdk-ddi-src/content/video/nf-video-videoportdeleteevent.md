---
UID: NF:video.VideoPortDeleteEvent
title: VideoPortDeleteEvent function
author: windows-driver-content
description: The VideoPortDeleteEvent function deletes the specified event object.
old-location: display\videoportdeleteevent.htm
old-project: display
ms.assetid: 0952f6ab-6d57-4ded-b167-74a7ace47961
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: VideoPortDeleteEvent, VideoPortDeleteEvent function [Display Devices], VideoPort_Functions_66e14d53-8a5e-4322-8576-4ac06230db31.xml, display.videoportdeleteevent, video/VideoPortDeleteEvent
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortDeleteEvent
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortDeleteEvent function


## -description


The <b>VideoPortDeleteEvent</b> function deletes the specified event object.


## -syntax


````
VP_STATUS VideoPortDeleteEvent(
  _In_ PVOID  HwDeviceExtension,
  _In_ PEVENT pEvent
);
````


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param pEvent [in]

Pointer to the event object to be deleted.


## -returns



<b>VideoPortDeleteEvent</b> returns NO_ERROR if the event object is successfully deleted.




## -remarks



This function should not be used to delete a mapped user event. To delete a mapped user event, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff565434">EngUnmapEvent</a>. 




## -see-also

<a href="..\video\nf-video-videoportcreateevent.md">VideoPortCreateEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565434">EngUnmapEvent</a>



 

 


