---
UID: NF:wdm.ExAcquireResourceExclusiveLite
title: ExAcquireResourceExclusiveLite function (wdm.h)
description: The ExAcquireResourceExclusiveLite routine acquires the given resource for exclusive access by the calling thread.
tech.root: kernel
ms.date: 01/05/2023
keywords: ["ExAcquireResourceExclusiveLite function"]
ms.keywords: ExAcquireResourceExclusiveLite, ExAcquireResourceExclusiveLite routine [Kernel-Mode Driver Architecture], k102_894dbc3c-af92-4916-8205-539062946dbe.xml, kernel.exacquireresourceexclusivelite, wdm/ExAcquireResourceExclusiveLite
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt:
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
req.irql: IRQL <= APC_LEVEL
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

## -description

The **ExAcquireResourceExclusiveLite** routine acquires the given resource for exclusive access by the calling thread.

## -parameters

### -param Resource [in, out]

A pointer to the resource to acquire.

### -param Wait [in]

Specifies the routine's behavior whenever the resource cannot be acquired immediately. If **TRUE**, the caller is put into a wait state until the resource can be acquired. If **FALSE**, the routine immediately returns, regardless of whether the resource can be acquired.

## -returns

**ExAcquireResourceExclusiveLite** returns **TRUE** if the resource is acquired. This routine returns **FALSE** if the input *Wait* is **FALSE** and exclusive access cannot be granted immediately.

## -remarks

The following list describes whether and when a caller is given exclusive access to a given resource:

- If the resource is currently not owned, exclusive access is granted immediately to the current thread.

- If the caller already had acquired the resource for exclusive access, the current thread is granted the same type of access recursively.-

- If the caller has shared access to the resource, the caller must release the lock before it attempts to reacquire it exclusively.

- If the resource is currently owned as exclusive by another thread, or if the caller only has shared access to the resource, the current thread is put into a wait state until the resource can be acquired.

If two threads each hold a shared lock on the same resource and both attempt to acquire the lock exclusively without releasing their shared lock, they will deadlock. This means that each thread will wait for the other to release its shared hold on the lock, and neither will release its shared hold until the other does.

The caller can release the resource by calling either [ExReleaseResourceLite](nf-wdm-exreleaseresourcelite.md) or [ExReleaseResourceForThreadLite](nf-wdm-exreleaseresourceforthreadlite.md).

Normal kernel APC delivery must be disabled before calling this routine. Disable normal kernel APC delivery by calling [KeEnterCriticalRegion](../ntddk/nf-ntddk-keentercriticalregion.md). Delivery must remain disabled until the resource is released, at which point it can be reenabled by calling [KeLeaveCriticalRegion](../ntddk/nf-ntddk-keleavecriticalregion.md). For more information, see [Disabling APCs](/windows-hardware/drivers/kernel/disabling-apcs).

## -see-also

[ExAcquireResourceSharedLite](nf-wdm-exacquireresourcesharedlite.md)

[ExGetExclusiveWaiterCount](nf-wdm-exgetexclusivewaitercount.md)

[ExGetSharedWaiterCount](nf-wdm-exgetsharedwaitercount.md)

[ExInitializeResourceLite](nf-wdm-exinitializeresourcelite.md)

[ExIsResourceAcquiredExclusiveLite](nf-wdm-exisresourceacquiredexclusivelite.md)

[ExReinitializeResourceLite](nf-wdm-exreinitializeresourcelite.md)

[ExReleaseResourceForThreadLite](nf-wdm-exreleaseresourceforthreadlite.md)

[ExReleaseResourceLite](nf-wdm-exreleaseresourcelite.md)

[KeEnterCriticalRegion](../ntddk/nf-ntddk-keentercriticalregion.md)

[KeLeaveCriticalRegion](../ntddk/nf-ntddk-keleavecriticalregion.md)
