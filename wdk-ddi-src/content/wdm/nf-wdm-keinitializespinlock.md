---
UID: NF:wdm.KeInitializeSpinLock
title: KeInitializeSpinLock function (wdm.h)
description: The KeInitializeSpinLock routine initializes a variable of type KSPIN_LOCK.
old-location: kernel\keinitializespinlock.htm
tech.root: kernel
ms.assetid: 84962db0-55ed-443c-84e3-2d8f3e9ec1d7
ms.date: 04/30/2018
ms.keywords: KeInitializeSpinLock, KeInitializeSpinLock routine [Kernel-Mode Driver Architecture], k105_715eff59-827a-4d41-8e3a-2ce0d1f1181d.xml, kernel.keinitializespinlock, wdm/KeInitializeSpinLock
ms.topic: function
f1_keywords:
 - "wdm/KeInitializeSpinLock"
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level (see Remarks section)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- KeInitializeSpinLock
product:
- Windows
targetos: Windows
req.typenames: 
---

# KeInitializeSpinLock function


## -description


The <b>KeInitializeSpinLock </b>routine initializes a variable of type KSPIN_LOCK.


## -parameters




### -param SpinLock [out]

Pointer to a spin lock, for which the caller must provide the storage.


## -returns



None




## -remarks



This routine must be called before an initial call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-keacquirespinlock">KeAcquireSpinLock</a>, to <a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551899(v=vs.85)">KeAcquireInStackQueuedSpinLock</a>, or to any other support routine that requires a spin lock as an argument.

Storage for a spin lock object must be resident: in the device extension of a driver-created device object, in the controller extension of a driver-created controller object, or in nonpaged pool allocated by the caller.

> [!NOTE]
> This function is inlined for x64 systems from Windows XP till Windows 7.
> Starting in Windows 8, this function is exported from `ntoskrnl.lib`. As a result, if you are using the Windows 10 WDK to build a binary that runs on Windows 7 (and therefore you need NX pool usage to pass Windows 10 HLK tests), you must define `WIN9X_COMPAT_SPINLOCK`.  Otherwise, you may see `Windows cannot load the device driver for this hardware. The driver may be corrupted or missing. (Code 39)`.

For more information about spin locks, see <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/spin-locks">Spin Locks</a>.

Callers of this routine can be running at any IRQL. Usually, a caller is running at IRQL = PASSIVE_LEVEL in an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nc-wdm-driver_add_device">AddDevice</a> routine.


## -see-also




<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551899(v=vs.85)">KeAcquireInStackQueuedSpinLock</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/drivers/ff551908(v=vs.85)">KeAcquireInStackQueuedSpinLockAtDpcLevel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-keacquirespinlock">KeAcquireSpinLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-keacquirespinlockatdpclevel">KeAcquireSpinLockAtDpcLevel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kereleaseinstackqueuedspinlock">KeReleaseInStackQueuedSpinLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kereleaseinstackqueuedspinlockfromdpclevel">KeReleaseInStackQueuedSpinLockFromDpcLevel</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kereleasespinlock">KeReleaseSpinLock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdm/nf-wdm-kereleasespinlockfromdpclevel">KeReleaseSpinLockFromDpcLevel</a>
 

 

