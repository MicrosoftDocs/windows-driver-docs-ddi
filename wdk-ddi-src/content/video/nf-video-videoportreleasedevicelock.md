---
UID: NF:video.VideoPortReleaseDeviceLock
title: VideoPortReleaseDeviceLock function
author: windows-driver-content
description: The VideoPortReleaseDeviceLock function releases the device lock acquired in a prior call to VideoPortAcquireDeviceLock.
old-location: display\videoportreleasedevicelock.htm
old-project: display
ms.assetid: 932953c3-828f-4dcd-918e-5b3b5d8def1c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: VideoPortReleaseDeviceLock, VideoPortReleaseDeviceLock function [Display Devices], VideoPort_Functions_509d905b-a70f-4932-975f-62d4c90c77b9.xml, display.videoportreleasedevicelock, video/VideoPortReleaseDeviceLock
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortReleaseDeviceLock
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortReleaseDeviceLock function


## -description


The <b>VideoPortReleaseDeviceLock</b> function releases the device lock acquired in a prior call to <a href="..\video\nf-video-videoportacquiredevicelock.md">VideoPortAcquireDeviceLock</a>.


## -syntax


````
VOID VideoPortReleaseDeviceLock(
  _In_ PVOID HwDeviceExtension
);
````


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


## -returns



None




## -remarks



Typically, the video port driver guarantees threaded synchronization into the miniport driver by using of a device lock. However, a miniport driver must perform its own synchronization when being accessed by a child device; that is, a miniport driver must perform synchronization in routines that it exposes through <a href="..\video\nc-video-pvideo_hw_query_interface.md">HwVidQueryInterface</a>. The miniport driver does this by calling <a href="..\video\nf-video-videoportacquiredevicelock.md">VideoPortAcquireDeviceLock</a> to acquire the device lock maintained by the video port driver.

The miniport driver should call <b>VideoPortReleaseDeviceLock</b> to release the device lock as quickly as possible. 




## -see-also

<a href="..\video\nc-video-pvideo_hw_query_interface.md">HwVidQueryInterface</a>



<a href="..\video\nf-video-videoportacquiredevicelock.md">VideoPortAcquireDeviceLock</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortReleaseDeviceLock function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

