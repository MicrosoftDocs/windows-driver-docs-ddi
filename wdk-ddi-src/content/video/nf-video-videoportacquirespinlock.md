---
UID: NF:video.VideoPortAcquireSpinLock
title: VideoPortAcquireSpinLock function (video.h)
description: The VideoPortAcquireSpinLock function obtains the specified spin lock.
old-location: display\videoportacquirespinlock.htm
tech.root: display
ms.assetid: 2e61ffb7-1720-47b2-b943-54ffa596cb08
ms.date: 05/10/2018
ms.keywords: VideoPortAcquireSpinLock, VideoPortAcquireSpinLock function [Display Devices], VideoPort_Functions_c25b68ac-032b-4b1c-bb15-93957f2e345c.xml, display.videoportacquirespinlock, video/VideoPortAcquireSpinLock
ms.topic: function
f1_keywords:
 - "video/VideoPortAcquireSpinLock"
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- Videoprt.sys
api_name:
- VideoPortAcquireSpinLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# VideoPortAcquireSpinLock function


## -description


The <b>VideoPortAcquireSpinLock</b> function obtains the specified spin lock.


## -parameters




### -param HwDeviceExtension [in, out]

Pointer to the miniport driver's device extension.


### -param SpinLock [in]

Pointer to a memory location that contains the spin lock.


### -param OldIrql [out]

Pointer to a memory location that will receive the current IRQL.


## -returns



None




## -remarks



The current IRQL is saved in <i>OldIrql</i>. Then, the current IRQL is reset to DISPATCH_LEVEL, and the specified spin lock is acquired.

The <i>OldIrql</i> value must be specified when the spin lock is released with <a href="https://msdn.microsoft.com/library/windows/hardware/ff570357">VideoPortReleaseSpinLock</a>.

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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff570176">VideoPortAcquireSpinLockAtDpcLevel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff570357">VideoPortReleaseSpinLock</a>
 

 

