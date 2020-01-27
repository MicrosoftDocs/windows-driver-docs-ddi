---
UID: NF:wdm.ExInitializePushLock
title: ExInitializePushLock function (wdm.h)
description: Initializes a push lock variable.
ms.assetid: fe5e8448-38e2-4317-99a7-1483649d5aeb
ms.date: 09/30/2018
f1_keywords:
 - "wdm/ExInitializePushLock"
ms.keywords: ExInitializePushLock
req.header: wdm.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name: 
- ExInitializePushLock
product:
- Windows
targetos: Windows


ms.custom: RS5
---

# ExInitializePushLock function


## -description

Initializes a push lock variable.

## -parameters

### -param PushLock

[Out] Pointer to the caller-supplied storage, which must be at least the value of sizeof(EX_PUSH_LOCK), for the push lock variable to be initialized. The storage must be 4-byte aligned on 32-bit platforms, and 8-byte aligned on 64-bit platforms.

## -remarks

Push locks are similar to ERESOURCE structures (also called "resources") in the following ways: 

- Push locks can be used for synchronization by a set of threads. 
- Push locks can be acquired for shared or exclusive access. 
- Although the caller provides the storage for the push lock variable, the EX_PUSH_LOCK structure is opaque: that is, its members are reserved for system use. 

Push locks offer the following advantages over ERESOURCE structures: 

- When push locks are mostly acquired for shared access, they are more efficient than ERESOURCE structures. 
- The storage for push locks can be allocated from paged or nonpaged pool. ERESOURCE structures must be allocated only from nonpaged pool. 
- EX_PUSH_LOCK structures are much smaller than ERESOURCE structures. 


Push locks have the following disadvantages when compared with ERESOURCE structures: 
- The algorithm for granting exclusive access is not fair to all threads. If there is a high level of exclusive-lock contention, there is no guarantee about the order in which threads will be granted exclusive access. 
- There are no support routines for determining the current owner of a push lock. (Users of ERESOURCE structures can call routines such as ExIsResourceAcquiredExclusiveLite to determine whether the current thread has exclusive access to the resource.)
- Push locks cannot be acquired recursively.


To acquire or release a push lock for exclusive access, call [**ExAcquirePushLockExclusive**](nf-wdm-exacquirepushlockexclusive.md) or [**ExReleasePushLockExclusive**](nf-wdm-exreleasepushlockexclusive.md), respectively.

To acquire or release a push lock for shared access, call [**ExAcquirePushLockShared**](nf-wdm-exacquirepushlockshared.md) or [**ExReleasePushLockShared**](nf-wdm-exreleasepushlockshared.md), respectively.

## -see-also
