---
UID: NF:fltkernel.FltInitializePushLock
title: FltInitializePushLock function (fltkernel.h)
description: Learn more about the FltInitializePushLock function.
tech.root: ifsk
ms.date: 10/03/2024
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: Windows XP SP2 Microsoft
req.target-min-winversvr: Windows Server 2003 SP1
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
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltInitializePushLock
 - fltkernel/FltInitializePushLock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltInitializePushLock
---

# FltInitializePushLock function

## -description

The **FltInitializePushLock** routine initializes a push lock variable.

## -parameters

### -param PushLock [out]

Pointer to the caller-supplied storage, which must be at least the value of **sizeof(**EX_PUSH_LOCK**)**, for the push lock variable to be initialized. The storage must be 4-byte aligned on 32-bit platforms, and 8-byte aligned on 64-bit platforms.

## -returns

None

## -remarks

A push lock is a synchronization primitive used to manage access to shared resources by multiple threads. Push locks are similar to [**ERESOURCE** structures](/windows-hardware/drivers/kernel/eresource-structures) (also called "resources") in the following ways:

* Push locks can be used for synchronization by a set of threads.

* Push locks can be acquired for shared or exclusive access.

* Although the caller provides the storage for the push lock variable, the EX_PUSH_LOCK structure is opaque: that is, its members are reserved for system use.

Push locks might not be the right choice for file system minifilters, because some of their characteristics can be incompatible with the inherently re-entrant nature of file systems.  

Push locks have the following *disadvantages* when compared with ERESOURCE structures:

* The algorithm for granting exclusive access isn't fair to all threads. If there is a high level of exclusive-lock contention, there's no guarantee about the order in which threads will be granted exclusive access.

* There are no support routines for determining the current owner of a push lock at run time. Users of ERESOURCE structures can call routines such as [**ExIsResourceAcquiredExclusiveLite**](../wdm/nf-wdm-exisresourceacquiredexclusivelite.md) to determine whether the current thread has exclusive access to the resource.

* There are no support extensions for determining the current owner of a push lock at debug time in order to diagnose deadlocks. Users of ERESOURCE structures can use the ```!locks``` extension in kd or windbg to determine the current owner.

* There is no driver verifier support to help early diagnosis of deadlocks through push locks.

* Exclusive push locks can't be acquired recursively.

Push locks offer the following *advantages* over ERESOURCE structures:

* When push locks are mostly acquired for shared access, they are more efficient than ERESOURCE structures.

* The storage for push locks can be allocated from paged or nonpaged pool. ERESOURCE structures must be allocated only from nonpaged pool.

* EX_PUSH_LOCK structures are much smaller than ERESOURCE structures.

Unless any of these advantages are compelling, an ERESOURCE is usually the more robust and maintainable solution to the Read/Write synchronization problem.

To acquire a push lock for exclusive access, call[**FltAcquirePushLockExclusive**](nf-fltkernel-fltacquirepushlockexclusive.md).

To acquire a push lock for shared access, call [**FltAcquirePushLockExclusive**](nf-fltkernel-fltacquirepushlockexclusive.md).

To release a push lock, call [**FltReleasePushLock**](nf-fltkernel-fltreleasepushlock.md).

To delete a push lock, call [**FltDeletePushLock**](nf-fltkernel-fltdeletepushlock.md).

## -see-also

[**ExIsResourceAcquiredExclusiveLite**](../wdm/nf-wdm-exisresourceacquiredexclusivelite.md)

[**FltAcquirePushLockExclusive**](nf-fltkernel-fltacquirepushlockexclusive.md)

[**FltAcquirePushLockShared**](nf-fltkernel-fltacquirepushlockshared.md)

[**FltDeletePushLock**](nf-fltkernel-fltdeletepushlock.md)

[**FltReleasePushLock**](nf-fltkernel-fltreleasepushlock.md)
