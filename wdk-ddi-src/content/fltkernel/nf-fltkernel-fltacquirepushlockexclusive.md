---
UID: NF:fltkernel.FltAcquirePushLockExclusive
title: FltAcquirePushLockExclusive macro (fltkernel.h)
description: The FltAcquirePushLockExclusive routine acquires the given push lock for exclusive access by the calling thread.
old-location: ifsk\fltacquirepushlockexclusive.htm
tech.root: ifsk
ms.date: 08/11/2022
keywords: ["FltAcquirePushLockExclusive macro"]
ms.keywords: FltAcquirePushLockExclusive, FltAcquirePushLockExclusive routine [Installable File System Drivers], FltApiRef_a_to_d_0f7b3360-aea2-42a8-bcc0-299d1915e4e0.xml, fltkernel/FltAcquirePushLockExclusive, ifsk.fltacquirepushlockexclusive
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
 - FltAcquirePushLockExclusive
 - fltkernel/FltAcquirePushLockExclusive
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - FltMgr.lib
 - FltMgr.dll
api_name:
 - FltAcquirePushLockExclusive
---

# FltAcquirePushLockExclusive macro

## -description

The **FltAcquirePushLockExclusive** macro acquires the given push lock for exclusive access by the calling thread.

## -parameters

### -param PushLock [in, out]

Opaque push lock pointer of type **PEX_PUSH_LOCK**. This pointer must have been initialized by a previous call to [**FltInitializePushLock**](nf-fltkernel-fltinitializepushlock.md).

## -returns

None.

## -remarks

**FltAcquirePushLockExclusive** acquires the given push lock for exclusive access by the calling thread.

Push locks are similar to ERESOURCE structures (also called resources) in that they can be acquired for shared or exclusive access. For more information about push locks, see the reference entry for [**FltInitializePushLock**](nf-fltkernel-fltinitializepushlock.md).

Unlike ERESOURCE structures, push locks cannot be acquired recursively. If the caller already has acquired the push lock for exclusive or shared access, the thread will hang.

When the caller will be given exclusive access to the given push lock depends on the following:

* If the push lock is currently unowned, exclusive access is granted immediately to the current thread.

* If the push lock has already been acquired for exclusive or shared access by another thread, the current thread is put into a wait state until the push lock can be acquired.

Because **FltAcquirePushLockExclusive** disables normal kernel APC delivery, it is not necessary to call [**KeEnterCriticalRegion**](../ntddk/nf-ntddk-keentercriticalregion.md) or [**FsRtlEnterFileSystem**](/windows-hardware/drivers/ifs/fsrtlenterfilesystem) before calling **FltAcquirePushLockExclusive**.

To release the push lock after it is acquired, call [**FltReleasePushLock**](nf-fltkernel-fltreleasepushlock.md). Every call to **FltAcquirePushLockExclusive** must be matched by a subsequent call to **FltReleasePushLock**.

To acquire a push lock for shared access, call [**FltAcquirePushLockShared**](nf-fltkernel-fltacquirepushlockshared.md).

To initialize a push lock, call [**FltInitializePushLock**](nf-fltkernel-fltinitializepushlock.md).

To delete a push lock, call [**FltDeletePushLock**](nf-fltkernel-fltdeletepushlock.md).

## -see-also

[**FltAcquirePushLockExclusiveEx**](nf-fltkernel-fltacquirepushlockexclusiveex.md)

[**FltAcquirePushLockShared**](nf-fltkernel-fltacquirepushlockshared.md)

[**FltDeletePushLock**](nf-fltkernel-fltdeletepushlock.md)

[**FltInitializePushLock**](nf-fltkernel-fltinitializepushlock.md)

[**FltReleasePushLock**](nf-fltkernel-fltreleasepushlock.md)

[**FsRtlEnterFileSystem**](/windows-hardware/drivers/ifs/fsrtlenterfilesystem)

[**KeEnterCriticalRegion**](../ntddk/nf-ntddk-keentercriticalregion.md)
