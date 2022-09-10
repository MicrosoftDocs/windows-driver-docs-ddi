---
UID: NF:fltkernel.FltAcquirePushLockShared
title: FltAcquirePushLockShared macro (fltkernel.h)
description: The FltAcquirePushLockShared routine acquires the given push lock for shared access by the calling thread.
old-location: ifsk\fltacquirepushlockshared.htm
tech.root: ifsk
ms.date: 08/11/2022
keywords: ["FltAcquirePushLockShared macro"]
ms.keywords: FltAcquirePushLockShared, FltAcquirePushLockShared routine [Installable File System Drivers], FltApiRef_a_to_d_329cb1e6-2fb5-45fa-a533-71a60ce341cf.xml, fltkernel/FltAcquirePushLockShared, ifsk.fltacquirepushlockshared
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.lib: FltMgr.lib
req.dll: 
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltAcquirePushLockShared
 - fltkernel/FltAcquirePushLockShared
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - FltMgr.lib
 - FltMgr.dll
api_name:
 - FltAcquirePushLockShared
---

# FltAcquirePushLockShared macro

## -description

The **FltAcquirePushLockShared** routine acquires the given push lock for shared access by the calling thread.

## -parameters

### -param PushLock [in, out]

Opaque push lock pointer of type **PEX_PUSH_LOCK**. This pointer must have been initialized by a previous call to [**FltInitializePushLock**](nf-fltkernel-fltinitializepushlock.md).

## -returns

None.

## -remarks

The **FltAcquirePushLockShared** routine acquires the given push lock for shared access by the calling thread.

Push locks are similar to ERESOURCE structures (also called resources) in that they can be acquired for shared or exclusive access. For more information about push locks, see the reference entry for [**FltInitializePushLock**](nf-fltkernel-fltinitializepushlock.md).

Unlike ERESOURCE structures, push locks cannot be acquired recursively. If the caller already has acquired the push lock for exclusive access, the system will hang. If the caller already has acquired the push lock for shared access, it can receive shared access again. However, each call to **FltAcquirePushLockShared** must be matched by a subsequent call to [**FltReleasePushLock**](nf-fltkernel-fltreleasepushlock.md).

When the caller will be given shared access to the given push lock depends on the following:

* If the push lock is currently unowned, shared access is granted immediately to the current thread.

* If the push lock has already been acquired for shared access by another thread and no thread is waiting for exclusive access to the push lock, shared access is granted to the caller immediately. The caller is put into a wait state if there is an exclusive waiter.

* If the push lock has already been acquired for exclusive access by another thread or if there is another thread waiting for exclusive access, the current thread is put into a wait state until the push lock can be acquired.

Because **FltAcquirePushLockShared** disables normal kernel APC delivery, it is not necessary to call [**KeEnterCriticalRegion**](../ntddk/nf-ntddk-keentercriticalregion.md)
 or [**FsRtlEnterFileSystem**](/windows-hardware/drivers/ifs/fsrtlenterfilesystem) before calling **FltAcquirePushLockShared**.

To release the push lock after it is acquired, call [**FltReleasePushLock**](nf-fltkernel-fltreleasepushlock.md). Every call to **FltAcquirePushLockShared** must be matched by a subsequent call to **FltReleasePushLock**.

To acquire a push lock for exclusive access, call [**FltAcquirePushLockExclusive**](nf-fltkernel-fltacquirepushlockexclusive.md).

To initialize a push lock, call [**FltInitializePushLock**](nf-fltkernel-fltinitializepushlock.md).

To delete a push lock, call [**FltDeletePushLock**](nf-fltkernel-fltdeletepushlock.md).

## -see-also

[**FltAcquirePushLockExclusive**](nf-fltkernel-fltacquirepushlockexclusive.md)

[**FltAcquirePushLockSharedEx**](nf-fltkernel-fltacquirepushlocksharedex.md)

[**FltDeletePushLock**](nf-fltkernel-fltdeletepushlock.md)

[**FltInitializePushLock**](nf-fltkernel-fltinitializepushlock.md)

[**FltReleasePushLock**](nf-fltkernel-fltreleasepushlock.md)

[**FsRtlEnterFileSystem**](/windows-hardware/drivers/ifs/fsrtlenterfilesystem)

[**KeEnterCriticalRegion**](../ntddk/nf-ntddk-keentercriticalregion.md)
