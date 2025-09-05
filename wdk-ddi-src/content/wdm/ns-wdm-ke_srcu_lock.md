---
UID: NS:wdm._KE_SRCU_LOCK
tech.root: kernel
title: KE_SRCU_LOCK structure (wdm.h)
ms.date: 09/02/2025
targetos: Windows
description: The KE_SRCU_LOCK structure represents the lock context used in SRCU read-side critical sections.
prerelease: false
ai-usage: ai-assisted
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.include-header: Wdm.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: Windows Server 2025
req.target-type: 
req.typenames: KE_SRCU_LOCK, *PKE_SRCU_LOCK
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _KE_SRCU_LOCK
 - PKE_SRCU_LOCK
 - KE_SRCU_LOCK
f1_keywords:
 - _KE_SRCU_LOCK
 - wdm/_KE_SRCU_LOCK
 - PKE_SRCU_LOCK
 - wdm/PKE_SRCU_LOCK
 - KE_SRCU_LOCK
 - wdm/KE_SRCU_LOCK
dev_langs:
 - c++
helpviewer_keywords:
 - _KE_SRCU_LOCK
---

## -description

The **KE_SRCU_LOCK** structure represents the lock context used in SRCU (Sleepable Read-Copy-Update) read-side critical sections.

## -struct-fields

### -field Placeholder[2]

An array of two `ULONG_PTR` values that serve as opaque storage for the SRCU lock context. The contents of this field are implementation-specific and should not be accessed or modified by drivers.

## -remarks

This structure is returned by [**KeSrcuReadLock**](nf-wdm-kesrcureadlock.md) and [**KeRcuReadLock**](nf-wdm-kercureadlock.md) functions and must be passed to the corresponding unlock functions.

This structure is opaque to drivers. Drivers should never:

- Access or modify the `Placeholder` field directly.
- Make assumptions about the structure's internal layout.
- Copy or serialize the structure contents.
- Use the structure across different SRCU partitions.

The structure is typically used in the following pattern:

```c
PSRCU_PARTITION SrcuPartition = KeSrcuAllocate();
KE_SRCU_LOCK LockContext;

// Enter read-side critical section
LockContext = KeSrcuReadLock(SrcuPartition);

// Access RCU-protected data safely
// ...

// Exit read-side critical section
KeSrcuReadUnlock(SrcuPartition, LockContext);
```

The lock context returned by the read lock function must be passed to the corresponding unlock function to properly exit the critical section. Using an incorrect or uninitialized lock context may result in system instability.

## -see-also

[**KeSrcuReadLock**](nf-wdm-kesrcureadlock.md)

[**KeSrcuReadUnlock**](nf-wdm-kesrcureadunlock.md)

[**KeRcuReadLock**](nf-wdm-kercureadlock.md)

[**KeRcuReadUnlock**](nf-wdm-kercureadunlock.md)

[**KeSrcuAllocate**](nf-wdm-kesrcuallocate.md)

[**KeSrcuSynchronize**](nf-wdm-kesrcusynchronize.md)
