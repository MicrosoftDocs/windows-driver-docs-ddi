---
UID: NF:fltkernel.FltAcquireResourceShared
tech.root: ifsk
title: FltAcquireResourceShared
ms.date: 03/03/2023
targetos: Windows
description: Learn more about the FltAcquireResourceShared function.
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
 - DllExport
api_location:
 - fltkernel.h
api_name:
 - FltAcquireResourceShared
f1_keywords:
 - FltAcquireResourceShared
 - fltkernel/FltAcquireResourceShared
dev_langs:
 - c++
helpviewer_keywords:
 - FltAcquireResourceShared
---

## -description

The **FltAcquireResourceShared** routine acquires the given resource for shared access by the calling thread.

## -parameters

### -param Resource [in/out]

Pointer to an opaque [**ERESOURCE**](/windows-hardware/drivers/kernel/eresource-structures) structure. This structure must be allocated by the caller from nonpaged pool and initialized by calling [**ExInitializeResourceLite**](../wdm/nf-wdm-exinitializeresourcelite.md) or [**ExReinitializeResourceLite**](../wdm/nf-wdm-exreinitializeresourcelite.md).

## -returns

None.

## -remarks

FltAcquireResourceShared routine acquires the given resource for shared access by the calling thread.

Whether or when the caller is given shared access to the given resource depends on the following:

* If the resource is currently unowned, shared access is granted immediately to the current thread.

* If the caller already has acquired the resource (for shared or exclusive access), the current thread is granted the same type of access recursively. Note that making this call does not convert a caller's exclusive ownership of a given resource to shared.

* If the resource is currently owned as shared by another thread and no thread is waiting for exclusive access to the resource, shared access is granted to the caller immediately. The caller is put into a wait state if there is an exclusive waiter.

* If the resource is currently owned as exclusive by another thread or if there is another thread waiting for exclusive access and the caller does not already have shared access to the resource, the current thread is put into a wait state until the resource can be acquired.

**FltAcquireResourceShared** is a wrapper for [**ExAcquireResourceSharedLite**](/previous-versions/ff544363(v=vs.85)) that disables normal kernel APC delivery.

Because **FltAcquireResourceShared** disables normal kernel APC delivery, it is not necessary to call [**KeEnterCriticalRegion**](../ntddk/nf-ntddk-keentercriticalregion.md) or [**FsRtlEnterFileSystem**](/windows-hardware/drivers/ifs/fsrtlenterfilesystem) before calling **FltAcquireResourceShared**.

To release the resource after it is acquired, call [**FltReleaseResource**](nf-fltkernel-fltreleaseresource.md). Every successful call to **FltAcquireResourceShared** must be matched by a subsequent call to **FltReleaseResource**.

To acquire a resource for exclusive access, call [**FltAcquireResourceExclusive**](nf-fltkernel-fltacquireresourceexclusive.md).

To delete a resource from the system's resource list, call [**ExDeleteResourceLite**](../wdm/nf-wdm-exdeleteresourcelite.md).

To initialize a resource for reuse, call [**ExReinitializeResourceLite**](../wdm/nf-wdm-exreinitializeresourcelite.md).

For more information about ERESOURCE structures, see [Introduction to ERESOURCE Routines](/windows-hardware/drivers/kernel/introduction-to-eresource-routines).
