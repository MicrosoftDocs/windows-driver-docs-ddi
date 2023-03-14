---
UID: NF:fltkernel.FltAcquireResourceExclusive
tech.root: ifsk
title: FltAcquireResourceExclusive
ms.date: 03/03/2023
targetos: Windows
description: Learn more about the FltAcquireResourceExclusive function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: fltkernel.h
req.idl: 
req.include-header: 
req.irql: IRQL <= APC_LEVEL
req.kmdf-ver: 
req.lib: FltMgr.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows XP SP2
req.target-min-winversvr: Windows Server 2003 SP1
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - 
api_location:
 - fltkernel.h
api_name:
 - FltAcquireResourceExclusive
f1_keywords:
 - FltAcquireResourceExclusive
 - fltkernel/FltAcquireResourceExclusive
dev_langs:
 - c++
helpviewer_keywords:
 - FltAcquireResourceExclusive
---

## -description

The **FltAcquireResourceExclusive** routine acquires the given resource for exclusive access by the calling thread.

## -parameters

### -param Resource [in/out]

A pointer to an opaque [**ERESOURCE**](/windows-hardware/drivers/kernel/eresource-structures) structure. This structure must be allocated by the caller from nonpaged pool and initialized by calling [**ExInitializeResourceLite**](../wdm/nf-wdm-exinitializeresourcelite.md) or [**ExReinitializeResourceLite**](../wdm/nf-wdm-exreinitializeresourcelite.md).

## -returns

None

## -remarks

**FltAcquireResourceExclusive** acquires the given resource for exclusive access by the calling thread.

The following circumstances determine whether or when the caller is given exclusive access to the given resource:

* If the resource is currently not owned, exclusive access is granted immediately to the current thread.

* If the caller already has acquired the resource for exclusive access, the current thread is granted the same type of access recursively.

* Callers who have shared access to the resource must release the lock and then reacquire it exclusively.

* If the resource is currently owned as exclusive by another thread, or if the caller only has shared access to the resource, the current thread is put into a wait state until the resource can be acquired.

If two threads each hold a shared lock on the same resource and both attempt to acquire the lock exclusively without releasing their shared lock, they will deadlock. This means that each thread will wait for the other to release its shared hold on the lock, and neither will release its shared hold until the other does.

**FltAcquireResourceExclusive** is a wrapper for [**ExAcquireResourceExclusiveLite**](/previous-versions/ff544351(v=vs.85)) that disables normal kernel APC delivery.

Because **FltAcquireResourceExclusive** disables normal kernel APC delivery, it is not necessary to call [**KeEnterCriticalRegion**](../ntddk/nf-ntddk-keentercriticalregion.md) or [**FsRtlEnterFileSystem**](fsrtlenterfilesystem.md) before calling **FltAcquireResourceExclusive**.

To release the resource after it is acquired, call [**FltReleaseResource**](nf-fltkernel-fltreleaseresource.md). Every successful call to **FltAcquireResourceExclusive** must be matched by a subsequent call to **FltReleaseResource**.

To acquire a resource for shared access, call [**FltAcquireResourceShared**](nf-fltkernel-fltacquireresourceshared.md).

To delete a resource from the system's resource list, call [**ExDeleteResourceLite**](../wdm/nf-wdm-exdeleteresourcelite.md).

To initialize a resource for reuse, call [**ExReinitializeResourceLite**](../wdm/nf-wdm-exreinitializeresourcelite.md).

For more information about ERESOURCE structures, see [Introduction to ERESOURCE Routines](/windows-hardware/drivers/kernel/introduction-to-eresource-routines).
