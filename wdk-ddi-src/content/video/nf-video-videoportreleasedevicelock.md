---
UID: NF:video.VideoPortReleaseDeviceLock
title: VideoPortReleaseDeviceLock function (video.h)
description: The VideoPortReleaseDeviceLock function releases the device lock acquired in a prior call to VideoPortAcquireDeviceLock.
old-location: display\videoportreleasedevicelock.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["VideoPortReleaseDeviceLock function"]
ms.keywords: VideoPortReleaseDeviceLock, VideoPortReleaseDeviceLock function [Display Devices], VideoPort_Functions_509d905b-a70f-4932-975f-62d4c90c77b9.xml, display.videoportreleasedevicelock, video/VideoPortReleaseDeviceLock
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
targetos: Windows
req.typenames: 
f1_keywords:
 - VideoPortReleaseDeviceLock
 - video/VideoPortReleaseDeviceLock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortReleaseDeviceLock
---

# VideoPortReleaseDeviceLock function


## -description

The <b>VideoPortReleaseDeviceLock</b> function releases the device lock acquired in a prior call to <a href="/windows-hardware/drivers/ddi/video/nf-video-videoportacquiredevicelock">VideoPortAcquireDeviceLock</a>.

## -parameters

### -param HwDeviceExtension 

[in]
Pointer to the miniport driver's device extension.

## -returns

None

## -remarks

Typically, the video port driver guarantees threaded synchronization into the miniport driver by using of a device lock. However, a miniport driver must perform its own synchronization when being accessed by a child device; that is, a miniport driver must perform synchronization in routines that it exposes through <a href="/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_query_interface">HwVidQueryInterface</a>. The miniport driver does this by calling <a href="/windows-hardware/drivers/ddi/video/nf-video-videoportacquiredevicelock">VideoPortAcquireDeviceLock</a> to acquire the device lock maintained by the video port driver.

The miniport driver should call <b>VideoPortReleaseDeviceLock</b> to release the device lock as quickly as possible.

## -see-also

<a href="/windows-hardware/drivers/ddi/video/nc-video-pvideo_hw_query_interface">HwVidQueryInterface</a>



<a href="/windows-hardware/drivers/ddi/video/nf-video-videoportacquiredevicelock">VideoPortAcquireDeviceLock</a>
