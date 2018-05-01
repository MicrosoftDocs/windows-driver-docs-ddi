---
UID: NF:video.VideoPortReleaseDeviceLock
title: VideoPortReleaseDeviceLock function
author: windows-driver-content
description: The VideoPortReleaseDeviceLock function releases the device lock acquired in a prior call to VideoPortAcquireDeviceLock.
old-location: display\videoportreleasedevicelock.htm
old-project: display
ms.assetid: 932953c3-828f-4dcd-918e-5b3b5d8def1c
ms.author: windowsdriverdev
ms.date: 4/16/2018
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
req.typenames: 
---

# VideoPortReleaseDeviceLock function


## -description


The <b>VideoPortReleaseDeviceLock</b> function releases the device lock acquired in a prior call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff570174">VideoPortAcquireDeviceLock</a>.


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


## -returns



None




## -remarks



Typically, the video port driver guarantees threaded synchronization into the miniport driver by using of a device lock. However, a miniport driver must perform its own synchronization when being accessed by a child device; that is, a miniport driver must perform synchronization in routines that it exposes through <a href="https://msdn.microsoft.com/f16a7fa3-3471-4ccb-b1b4-982d33f930d3">HwVidQueryInterface</a>. The miniport driver does this by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff570174">VideoPortAcquireDeviceLock</a> to acquire the device lock maintained by the video port driver.

The miniport driver should call <b>VideoPortReleaseDeviceLock</b> to release the device lock as quickly as possible. 




## -see-also




<a href="https://msdn.microsoft.com/f16a7fa3-3471-4ccb-b1b4-982d33f930d3">HwVidQueryInterface</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570174">VideoPortAcquireDeviceLock</a>
 

 

