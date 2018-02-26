---
UID: NF:video.VideoPortAcquireDeviceLock
title: VideoPortAcquireDeviceLock function
author: windows-driver-content
description: The VideoPortAcquireDeviceLock function acquires the device lock maintained by the video port driver.
old-location: display\videoportacquiredevicelock.htm
old-project: display
ms.assetid: eeb2d1ad-ad99-4099-9560-8653a627aa08
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , A, D, L, P, V, VideoPortAcquireDeviceLock, VideoPortAcquireDeviceLock function [Display Devices], VideoPort_Functions_4c588378-53be-496c-93f0-0d285b8a1a05.xml, c, d, display.videoportacquiredevicelock, e, i, k, o, q, r, t, u, v, video/VideoPortAcquireDeviceLock"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Videoprt.sys
apiname:
-	VideoPortAcquireDeviceLock
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortAcquireDeviceLock function


## -description


The <b>VideoPortAcquireDeviceLock</b> function acquires the device lock maintained by the video port driver.


## -syntax


````
VOID VideoPortAcquireDeviceLock(
  _In_ PVOID HwDeviceExtension
);
````


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


## -returns



None




## -remarks



Typically, the video port driver guarantees threaded synchronization into the miniport driver through the use of a device lock. However, a miniport driver must perform its own synchronization when being accessed by a child device. That is, a miniport driver must perform synchronization in routines that it exposes through <a href="..\video\nc-video-pvideo_hw_query_interface.md">HwVidQueryInterface</a> by acquiring the device lock maintained by the video port driver.

The miniport driver should release the device lock as quickly as possible by calling <a href="..\video\nf-video-videoportreleasedevicelock.md">VideoPortReleaseDeviceLock</a>.




## -see-also

<a href="..\video\nc-video-pvideo_hw_query_interface.md">HwVidQueryInterface</a>



<a href="..\video\nf-video-videoportreleasedevicelock.md">VideoPortReleaseDeviceLock</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortAcquireDeviceLock function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

