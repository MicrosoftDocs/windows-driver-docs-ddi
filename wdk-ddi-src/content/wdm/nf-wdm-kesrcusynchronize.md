---
UID: NF:wdm.KeSrcuSynchronize
tech.root: kernel
title: KeSrcuSynchronize function (wdm.h)
ms.date: 09/02/2025
targetos: Windows
description: The KeSrcuSynchronize routine waits until all currently active read-side critical sections for a Sleepable Read-Copy-Update (SRCU) partition have exited.
prerelease: false
ai-usage: ai-assisted
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: NtosKrnl.exe
req.header: wdm.h
req.idl: 
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.irql: < DISPATCH_LEVEL
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
 - KeSrcuSynchronize
f1_keywords:
 - KeSrcuSynchronize
 - wdm/KeSrcuSynchronize
dev_langs:
 - c++
helpviewer_keywords:
 - KeSrcuSynchronize
---

## -description

The **KeSrcuSynchronize** routine waits until all currently active read-side critical sections for a Sleepable Read-Copy-Update (SRCU) partition have exited.

## -parameters

### -param Rcu [in]

A pointer to the SRCU instance that was previously allocated by [**KeSrcuAllocate**](nf-wdm-kesrcuallocate.md).

## -remarks

**KeSrcuSynchronize** implements the "synchronize" operation for SRCU, which starts a grace period and waits for all currently active readers to exit their critical sections. This function is essential for safe memory reclamation and data structure updates.

The grace period semantics are as follows:

- The function waits only for readers that were active when the call was made.
- New readers that enter after the call begins are not included in the wait.
- The function might block until all target readers call [**KeSrcuReadUnlock**](nf-wdm-kesrcureadunlock.md).
- Multiple synchronize operations can be in progress simultaneously.

Call this function only at IRQL < DISPATCH_LEVEL since it may block. This function can sleep, making it suitable for pageable code. Don't call this function from within an SRCU read-side critical section.

The typical writer pattern is as follows:

1. Remove data structure from global visibility.
2. Call **KeSrcuSynchronize** to wait for existing readers.
3. Safely deallocate or modify the data structure.

The function ensures that no readers are accessing the data when it returns, making it safe to perform updates or memory reclamation.

## -see-also

[**KeSrcuAllocate**](nf-wdm-kesrcuallocate.md)

[**KeSrcuFree**](nf-wdm-kesrcufree.md)

[**KeSrcuReadLock**](nf-wdm-kesrcureadlock.md)

[**KeSrcuReadUnlock**](nf-wdm-kesrcureadunlock.md)
