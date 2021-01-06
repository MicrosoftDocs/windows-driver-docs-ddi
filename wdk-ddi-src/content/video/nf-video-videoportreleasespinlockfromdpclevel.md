---
UID: NF:video.VideoPortReleaseSpinLockFromDpcLevel
title: VideoPortReleaseSpinLockFromDpcLevel function (video.h)
description: The VideoPortReleaseSpinLockFromDpcLevel function releases the spin lock obtained by a previous call to VideoPortAcquireSpinLockAtDpcLevel.
old-location: display\videoportreleasespinlockfromdpclevel.htm
tech.root: display
ms.date: 03/29/2018
keywords: ["VideoPortReleaseSpinLockFromDpcLevel function"]
ms.keywords: VideoPortReleaseSpinLockFromDpcLevel, VideoPortReleaseSpinLockFromDpcLevel function [Display Devices], VideoPort_Functions_2c3a3aa1-4ef4-4b7f-8cdf-b658a1128c35.xml, display.videoportreleasespinlockfromdpclevel, video/VideoPortReleaseSpinLockFromDpcLevel
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
req.irql: DISPATCH_LEVEL
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
f1_keywords:
 - VideoPortReleaseSpinLockFromDpcLevel
 - video/VideoPortReleaseSpinLockFromDpcLevel
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - Videoprt.sys
api_name:
 - VideoPortReleaseSpinLockFromDpcLevel
---

# VideoPortReleaseSpinLockFromDpcLevel function


## -description

The <b>VideoPortReleaseSpinLockFromDpcLevel</b> function releases the spin lock obtained by a previous call to <a href="/previous-versions/ff570176(v=vs.85)">VideoPortAcquireSpinLockAtDpcLevel</a>.

## -parameters

### -param HwDeviceExtension 

[in] Pointer to the miniport driver's device extension.

### -param SpinLock 

[in, out] Pointer to a memory location that contains the spin lock to be released.

## -returns

None

## -remarks

Miniport drivers call <b>VideoPortReleaseSpinLockFromDpcLevel</b> to release a spin lock acquired by calling <a href="/previous-versions/ff570176(v=vs.85)">VideoPortAcquireSpinLockAtDpcLevel</a>.

It is an error to call <b>VideoPortReleaseSpinLockFromDpcLevel</b> if the given spin lock was acquired by calling <a href="/previous-versions/ff570175(v=vs.85)">VideoPortAcquireSpinLock</a> because the caller's original IRQL is not restored, which can cause deadlocks or fatal page faults.

## -see-also

<a href="/previous-versions/ff570175(v=vs.85)">VideoPortAcquireSpinLock</a>



<a href="/previous-versions/ff570176(v=vs.85)">VideoPortAcquireSpinLockAtDpcLevel</a>
