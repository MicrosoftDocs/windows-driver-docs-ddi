---
UID: NF:wdm.ExAcquireResourceSharedLite
title: ExAcquireResourceSharedLite function (wdm.h)
description: The ExAcquireResourceSharedLite routine acquires the given resource for shared access by the calling thread.
old-location: kernel\exacquireresourcesharedlite.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["ExAcquireResourceSharedLite function"]
ms.keywords: ExAcquireResourceSharedLite, ExAcquireResourceSharedLite routine [Kernel-Mode Driver Architecture], k102_da765a3d-5d09-43da-98fe-48d4f7bccb9b.xml, kernel.exacquireresourcesharedlite, wdm/ExAcquireResourceSharedLite
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlExApcLte3, WithinCriticalRegion, HwStorPortProhibitedDDIs, WithinCriticalRegion(storport)
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
 - ExAcquireResourceSharedLite
 - wdm/ExAcquireResourceSharedLite
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExAcquireResourceSharedLite
---

# ExAcquireResourceSharedLite function


## -description

The **ExAcquireResourceSharedLite** routine acquires the given resource for shared access by the calling thread.

## -parameters

### -param Resource 

[in, out]
A pointer to the resource to acquire.

### -param Wait 

[in]
Specifies the routine's behavior whenever the resource cannot be acquired immediately. If **TRUE**, the caller is put into a wait state until the resource can be acquired. If **FALSE**, the routine immediately returns, regardless of whether the resource can be acquired.

## -returns

The caller can release the resource by calling either [ExReleaseResourceLite](nf-wdm-exreleaseresourcelite.md) or [ExReleaseResourceForThreadLite](nf-wdm-exreleaseresourceforthreadlite.md).

**ExAcquireResourceSharedLite** returns **TRUE** if (or when) the resource is acquired. This routine returns **FALSE** if the input *Wait* is **FALSE** and shared access cannot be granted immediately.

## -remarks

Whether or when the caller is given shared access to the given resource depends on the following:

* If the resource is currently unowned, shared access is granted immediately to the current thread.

* If the caller already has acquired the resource (for shared or exclusive access), the current thread is granted the same type of access recursively. Note that making this call does not convert a caller's exclusive access of a given resource to shared access.

* If the resource is currently owned as shared by another thread and no thread is waiting for exclusive access to the resource, shared access is granted to the caller immediately. The caller is put into a wait state if there is an exclusive waiter.

* If the resource is currently owned as exclusive by another thread or if there is another thread waiting for exclusive access and the caller does not already have shared access to the resource, the current thread either is put into a wait state (*Wait* set to **TRUE**) or **ExAcquireResourceSharedLite** returns **FALSE**.

Normal kernel APC delivery must be disabled before calling this routine. Disable normal kernel APC delivery by calling [KeEnterCriticalRegion](../ntddk/nf-ntddk-keentercriticalregion.md). Delivery must remain disabled until the resource is released, at which point it can be reenabled by calling [KeLeaveCriticalRegion](../ntddk/nf-ntddk-keleavecriticalregion.md). For more information, see [Disabling APCs](/windows-hardware/drivers/kernel/disabling-apcs).

## -see-also

[ExAcquireResourceExclusiveLite](nf-wdm-exacquireresourceexclusivelite.md)

[ExAcquireSharedStarveExclusive](nf-wdm-exacquiresharedstarveexclusive.md)

[ExAcquireSharedWaitForExclusive](nf-wdm-exacquiresharedwaitforexclusive.md)

[ExConvertExclusiveToSharedLite](nf-wdm-exconvertexclusivetosharedlite.md)

[ExGetExclusiveWaiterCount](nf-wdm-exgetexclusivewaitercount.md)

[ExGetSharedWaiterCount](nf-wdm-exgetsharedwaitercount.md)

[ExInitializeResourceLite](nf-wdm-exinitializeresourcelite.md)

[ExIsResourceAcquiredSharedLite](nf-wdm-exisresourceacquiredsharedlite.md)

[ExReinitializeResourceLite](nf-wdm-exreinitializeresourcelite.md)

[ExReleaseResourceForThreadLite](nf-wdm-exreleaseresourceforthreadlite.md)
