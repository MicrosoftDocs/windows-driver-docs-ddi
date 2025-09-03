---
UID: NF:wdm.KeSrcuReadLock
tech.root: kernel
title: KeSrcuReadLock function (wdm.h)
ms.date: 09/02/2025
targetos: Windows
description: The KeSrcuReadLock routine enters a read-side critical section for a Sleepable Read-Copy-Update (SRCU) partition.
prerelease: false
ai-usage: ai-assisted
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: NtosKrnl.exe
req.header: wdm.h
req.idl: 
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.irql: Any level
req.kmdf-ver: 
req.lib: NtosKrnl.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: Universal
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeSrcuReadLock
f1_keywords:
 - KeSrcuReadLock
 - wdm/KeSrcuReadLock
dev_langs:
 - c++
helpviewer_keywords:
 - KeSrcuReadLock
---

## -description

The **KeSrcuReadLock** routine enters the read-side RCU critical section of a specified Sleepable Read-Copy-Update (SRCU) partition.

## -parameters

### -param Rcu [in]

A pointer to the SRCU instance that was previously allocated by [**KeSrcuAllocate**](nf-wdm-kesrcuallocate.md).

### -param Lock [out]

A pointer to a [**KE_SRCU_LOCK**](ns-wdm-ke_srcu_lock.md) structure that receives the lock context. This context must be passed to [**KeSrcuReadUnlock**](nf-wdm-kesrcureadunlock.md) when exiting the critical section.

## -remarks

**KeSrcuReadLock** enters a read-side critical section, allowing the caller to safely access data protected by the SRCU partition. Multiple readers can hold read locks simultaneously, but updates must wait for all readers to exit.

Unlike regular RCU, readers can sleep while holding the read lock. Read locks can be nested within the same thread. The thread can migrate to different processors while holding the lock.

Always pair with [**KeSrcuReadUnlock**](nf-wdm-kesrcureadunlock.md) in the same thread. The **Lock** parameter receives context needed for unlocking. Multiple readers can access the protected data concurrently. Writers must use [**KeSrcuSynchronize**](nf-wdm-kesrcusynchronize.md) to wait for reader completion.

If the thread migrates to a different processor between lock and unlock, the unlock operation will use an inter-processor interrupt (IPI) to complete the unlock on the original processor.

## -see-also

[**KE_SRCU_LOCK**](ns-wdm-ke_srcu_lock.md)

[**KeSrcuAllocate**](nf-wdm-kesrcuallocate.md)

[**KeSrcuFree**](nf-wdm-kesrcufree.md)

[**KeSrcuReadUnlock**](nf-wdm-kesrcureadunlock.md)

[**KeSrcuSynchronize**](nf-wdm-kesrcusynchronize.md)
