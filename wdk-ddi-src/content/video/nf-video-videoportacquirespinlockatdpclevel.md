---
UID: NF:video.VideoPortAcquireSpinLockAtDpcLevel
title: VideoPortAcquireSpinLockAtDpcLevel function (video.h)
description: The VideoPortAcquireSpinLockAtDpcLevel function acquires a spin lock when the caller is already running at IRQL = DISPATCH_LEVEL.
old-location: display\videoportacquirespinlockatdpclevel.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["VideoPortAcquireSpinLockAtDpcLevel function"]
ms.keywords: VideoPortAcquireSpinLockAtDpcLevel, VideoPortAcquireSpinLockAtDpcLevel function [Display Devices], VideoPort_Functions_fc52bdfd-6f1a-4f5c-93e6-321d2488bcd5.xml, display.videoportacquirespinlockatdpclevel, video/VideoPortAcquireSpinLockAtDpcLevel
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
req.irql: DISPATCH_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - VideoPortAcquireSpinLockAtDpcLevel
 - video/VideoPortAcquireSpinLockAtDpcLevel
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortAcquireSpinLockAtDpcLevel
---

# VideoPortAcquireSpinLockAtDpcLevel function


## -description

The <b>VideoPortAcquireSpinLockAtDpcLevel</b> function acquires a spin lock when the caller is already running at IRQL = DISPATCH_LEVEL.

## -parameters

### -param HwDeviceExtension 

[in, out]
Pointer to the miniport driver's device extension.

### -param SpinLock 

[in]
Pointer to a memory location that contains the spin lock.

## -returns

None

## -remarks

Miniport drivers call <b>VideoPortAcquireSpinLockAtDpcLevel</b> instead of <a href="/previous-versions/ff570175(v=vs.85)">VideoPortAcquireSpinLock</a> for better driver performance if and only if they are already running at IRQL = DISPATCH_LEVEL.

If a miniport driver is running at IRQL < DISPATCH_LEVEL, it should call <b>VideoPortAcquireSpinLock</b> to have IRQL raised by that routine. <b>VideoPortAcquireSpinLockAtDpcLevel</b> requires the caller to be running already at IRQL = DISPATCH_LEVEL, so no raise is necessary.

The caller should release the spin lock with <a href="/previous-versions/ff570358(v=vs.85)">VideoPortReleaseSpinLockFromDpcLevel</a> as quickly as possible.

## -see-also

<a href="/previous-versions/ff570175(v=vs.85)">VideoPortAcquireSpinLock</a>



<a href="/previous-versions/ff570358(v=vs.85)">VideoPortReleaseSpinLockFromDpcLevel</a>
