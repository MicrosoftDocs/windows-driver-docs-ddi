---
UID: NF:wdm.ExAcquireResourceExclusiveLite
title: ExAcquireResourceExclusiveLite function (wdm.h)
description: The ExAcquireResourceExclusiveLite routine acquires the given resource for exclusive access by the calling thread.
old-location: kernel\exacquireresourceexclusivelite.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["ExAcquireResourceExclusiveLite function"]
ms.keywords: ExAcquireResourceExclusiveLite, ExAcquireResourceExclusiveLite routine [Kernel-Mode Driver Architecture], k102_894dbc3c-af92-4916-8205-539062946dbe.xml, kernel.exacquireresourceexclusivelite, wdm/ExAcquireResourceExclusiveLite
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: ExclusiveResourceAccess, IrqlExApcLte3, WithinCriticalRegion, HwStorPortProhibitedDDIs, WithinCriticalRegion(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - ExAcquireResourceExclusiveLite
 - wdm/ExAcquireResourceExclusiveLite
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExAcquireResourceExclusiveLite
---

# ExAcquireResourceExclusiveLite function


## -description

The <b>ExAcquireResourceExclusiveLite</b> routine acquires the given resource for exclusive access by the calling thread.

## -parameters

### -param Resource 

[in, out]
A pointer to the resource to acquire.

### -param Wait 

[in]
Specifies the routine's behavior whenever the resource cannot be acquired immediately. If <b>TRUE</b>, the caller is put into a wait state until the resource can be acquired. If <b>FALSE</b>, the routine immediately returns, regardless of whether the resource can be acquired.

## -returns

<b>ExAcquireResourceExclusiveLite</b> returns <b>TRUE</b> if the resource is acquired. This routine returns <b>FALSE</b> if the input <i>Wait</i> is <b>FALSE</b> and exclusive access cannot be granted immediately.

## -remarks

The following list describes whether and when a caller is given exclusive access to a given resource:

<ul>
<li>
If the resource is currently not owned, exclusive access is granted immediately to the current thread.

</li>
<li>
If the caller already had acquired the resource for exclusive access, the current thread is granted the same type of access recursively.

</li>
<li>
If the caller has shared access to the resource, the caller must release the lock before it attempts to reacquire it exclusively.

</li>
<li>
If the resource is currently owned as exclusive by another thread, or if the caller only has shared access to the resource, the current thread is put into a wait state until the resource can be acquired.

</li>
</ul>
<div class="alert"><b>Note</b>    If two threads each hold a shared lock on the same resource and both attempt to acquire the lock exclusively without releasing their shared lock, they will deadlock. This means that each thread will wait for the other to release its shared hold on the lock, and neither will release its shared hold until the other does.</div>
<div> </div>
The caller can release the resource by calling either <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exreleaseresourcelite">ExReleaseResourceLite</a> or <a href="/previous-versions/ff545585(v=vs.85)">ExReleaseResourceForThreadLite</a>.

Normal kernel APC delivery must be disabled before calling this routine. Disable normal kernel APC delivery by calling <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-keentercriticalregion">KeEnterCriticalRegion</a>. Delivery must remain disabled until the resource is released, at which point it can be reenabled by calling <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-keleavecriticalregion">KeLeaveCriticalRegion</a>. For more information, see <a href="/windows-hardware/drivers/kernel/disabling-apcs">Disabling APCs</a>.

## -see-also

<a href="/previous-versions/ff544363(v=vs.85)">ExAcquireResourceSharedLite</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exgetexclusivewaitercount">ExGetExclusiveWaiterCount</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exgetsharedwaitercount">ExGetSharedWaiterCount</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exinitializeresourcelite">ExInitializeResourceLite</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exisresourceacquiredexclusivelite">ExIsResourceAcquiredExclusiveLite</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exreinitializeresourcelite">ExReinitializeResourceLite</a>



<a href="/previous-versions/ff545585(v=vs.85)">ExReleaseResourceForThreadLite</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-keentercriticalregion">KeEnterCriticalRegion</a>
