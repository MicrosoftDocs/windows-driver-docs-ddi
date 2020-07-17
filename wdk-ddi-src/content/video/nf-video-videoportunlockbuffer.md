---
UID: NF:video.VideoPortUnlockBuffer
title: VideoPortUnlockBuffer function (video.h)
description: The VideoPortUnLockBuffer function unlocks physical pages described by the specified memory descriptor list (MDL).
old-location: display\videoportunlockbuffer.htm
tech.root: display
ms.assetid: d5d34f32-026b-4c9f-86ae-a835d4e9c381
ms.date: 05/10/2018
keywords: ["VideoPortUnlockBuffer function"]
ms.keywords: VideoPortUnlockBuffer, VideoPortUnlockBuffer function [Display Devices], VideoPort_Functions_2cb5a81f-1956-4431-bf54-7ee6e3d79eab.xml, display.videoportunlockbuffer, video/VideoPortUnlockBuffer
f1_keywords:
 - "video/VideoPortUnlockBuffer"
 - "VideoPortUnlockBuffer"
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
- VideoPortUnlockBuffer
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortUnlockBuffer function


## -description


The <b>VideoPortUnLockBuffer</b> function unlocks physical pages described by the specified memory descriptor list (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a>).


## -parameters




### -param HwDeviceExtension [in]

Pointer to the miniport driver's device extension.


### -param Mdl [in]

Pointer to the MDL of the buffer to be released. This parameter should be the same pointer that was returned by <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportlockbuffer">VideoPortLockBuffer</a>.


## -returns



None




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/video/nf-video-videoportlockbuffer">VideoPortLockBuffer</a>
 

 

