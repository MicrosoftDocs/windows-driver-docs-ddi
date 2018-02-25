---
UID: NF:video.VideoPortAcquireSpinLockAtDpcLevel
title: VideoPortAcquireSpinLockAtDpcLevel function
author: windows-driver-content
description: The VideoPortAcquireSpinLockAtDpcLevel function acquires a spin lock when the caller is already running at IRQL = DISPATCH_LEVEL.
old-location: display\videoportacquirespinlockatdpclevel.htm
old-project: display
ms.assetid: 72c6e923-e7c0-4d3d-a115-33e3e11053eb
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , A, D, L, P, S, V, VideoPortAcquireSpinLockAtDpcLevel, VideoPortAcquireSpinLockAtDpcLevel function [Display Devices], VideoPort_Functions_fc52bdfd-6f1a-4f5c-93e6-321d2488bcd5.xml, c, d, display.videoportacquirespinlockatdpclevel, e, i, k, l, n, o, p, q, r, t, u, v, video/VideoPortAcquireSpinLockAtDpcLevel"
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
req.irql: DISPATCH_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Videoprt.sys
apiname:
-	VideoPortAcquireSpinLockAtDpcLevel
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortAcquireSpinLockAtDpcLevel function


## -description


The <b>VideoPortAcquireSpinLockAtDpcLevel</b> function acquires a spin lock when the caller is already running at IRQL = DISPATCH_LEVEL.


## -syntax


````
VOID VideoPortAcquireSpinLockAtDpcLevel(
  _Inout_ PVOID      HwDeviceExtension,
  _In_    PSPIN_LOCK SpinLock
);
````


## -parameters




### -param HwDeviceExtension [in, out]

Pointer to the miniport driver's device extension.


### -param param

TBD




#### - SpinLock [in]

Pointer to a memory location that contains the spin lock.


## -returns



None




## -remarks



Miniport drivers call <b>VideoPortAcquireSpinLockAtDpcLevel</b> instead of <a href="..\video\nf-video-videoportacquirespinlock.md">VideoPortAcquireSpinLock</a> for better driver performance if and only if they are already running at IRQL = DISPATCH_LEVEL.

If a miniport driver is running at IRQL &lt; DISPATCH_LEVEL, it should call <b>VideoPortAcquireSpinLock</b> to have IRQL raised by that routine. <b>VideoPortAcquireSpinLockAtDpcLevel</b> requires the caller to be running already at IRQL = DISPATCH_LEVEL, so no raise is necessary.

The caller should release the spin lock with <a href="..\video\nf-video-videoportreleasespinlockfromdpclevel.md">VideoPortReleaseSpinLockFromDpcLevel</a> as quickly as possible.




## -see-also

<a href="..\video\nf-video-videoportreleasespinlockfromdpclevel.md">VideoPortReleaseSpinLockFromDpcLevel</a>



<a href="..\video\nf-video-videoportacquirespinlock.md">VideoPortAcquireSpinLock</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortAcquireSpinLockAtDpcLevel function%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

