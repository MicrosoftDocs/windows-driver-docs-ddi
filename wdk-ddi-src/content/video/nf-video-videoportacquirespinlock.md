---
UID: NF:video.VideoPortAcquireSpinLock
title: VideoPortAcquireSpinLock function
author: windows-driver-content
description: The VideoPortAcquireSpinLock function obtains the specified spin lock.
old-location: display\videoportacquirespinlock.htm
old-project: display
ms.assetid: 2e61ffb7-1720-47b2-b943-54ffa596cb08
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: video/VideoPortAcquireSpinLock, display.videoportacquirespinlock, VideoPortAcquireSpinLock, VideoPortAcquireSpinLock function [Display Devices], VideoPort_Functions_c25b68ac-032b-4b1c-bb15-93957f2e345c.xml
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Videoprt.sys
apiname:
-	VideoPortAcquireSpinLock
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---

# VideoPortAcquireSpinLock function


## -description


The <b>VideoPortAcquireSpinLock</b> function obtains the specified spin lock.


## -syntax


````
VOID VideoPortAcquireSpinLock(
  _Inout_ PVOID      HwDeviceExtension,
  _In_    PSPIN_LOCK SpinLock,
  _Out_   PUCHAR     OldIrql
);
````


## -parameters




#### - HwDeviceExtension [in, out]

Pointer to the miniport driver's device extension.


### -param param

TBD


#### - OldIrql [out]

Pointer to a memory location that will receive the current IRQL.


#### - SpinLock [in]

Pointer to a memory location that contains the spin lock.


## -returns


None



## -remarks


The current IRQL is saved in <i>OldIrql</i>. Then, the current IRQL is reset to DISPATCH_LEVEL, and the specified spin lock is acquired.

The <i>OldIrql</i> value must be specified when the spin lock is released with <a href="..\video\nf-video-videoportreleasespinlock.md">VideoPortReleaseSpinLock</a>.

Spin locks can cause serious problems if not used judiciously. In particular, no deadlock protection is performed and dispatching is disabled while the spin lock is held. Therefore: 
<ul>
<li>
The code within a critical region guarded by a spin lock must neither be pageable nor make any references to pageable data. 

</li>
<li>
The code within a critical region guarded by a spin lock can neither call any external function that might access pageable data or raise an exception, nor can it generate any exceptions. 

</li>
<li>
The caller should release the spin lock with <b>VideoPortReleaseSpinLock</b> as quickly as possible. 

</li>
</ul>


## -see-also

<a href="..\video\nf-video-videoportacquirespinlockatdpclevel.md">VideoPortAcquireSpinLockAtDpcLevel</a>

<a href="..\video\nf-video-videoportreleasespinlock.md">VideoPortReleaseSpinLock</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortAcquireSpinLock function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

