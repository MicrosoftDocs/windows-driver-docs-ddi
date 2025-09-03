---
UID: NF:wdm.KeSrcuAllocate
tech.root: kernel
title: KeSrcuAllocate function (wdm.h)
ms.date: 09/02/2025
targetos: Windows
description: The KeSrcuAllocate routine allocates and initializes a Sleepable Read-Copy-Update (SRCU) partition for synchronization purposes.
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
 - KeSrcuAllocate
f1_keywords:
 - KeSrcuAllocate
 - wdm/KeSrcuAllocate
dev_langs:
 - c++
helpviewer_keywords:
 - KeSrcuAllocate
---

## -description

The **KeSrcuAllocate** routine allocates and initializes a sleepable Read-Copy-Update (SRCU) partition for synchronization purposes.

## -parameters

### -param Tag [in]

A four-character tag value used to identify this SRCU instance.

## -returns

**KeSrcuAllocate** returns a pointer to the allocated SRCU instance on success, or NULL if the allocation fails.

## -remarks

**KeSrcuAllocate** creates a new SRCU synchronization domain that allows multiple readers to access shared data concurrently while ensuring safe updates. SRCU differs from regular RCU in that readers can sleep while holding the read lock.

The SRCU partition returned by this function must be freed using [**KeSrcuFree**](nf-wdm-kesrcufree.md) when no longer needed.

Each SRCU partition is independent and maintains its own grace periods. SRCU is designed for scenarios where readers may need to sleep or perform blocking operations.

The *Tag* parameter should be unique to help identify the instance during debugging.

### Typical Usage Pattern

* Call **KeSrcuAllocate** to create an SRCU partition.
* Use [**KeSrcuReadLock**](nf-wdm-kesrcureadlock.md) and [**KeSrcuReadUnlock**](nf-wdm-kesrcureadunlock.md) for reader synchronization.
* Use [**KeSrcuSynchronize**](nf-wdm-kesrcusynchronize.md) to wait for reader completion before updates.
* Call [**KeSrcuFree**](nf-wdm-kesrcufree.md) to clean up when done.

## -see-also

[**KeSrcuFree**](nf-wdm-kesrcufree.md)

[**KeSrcuReadLock**](nf-wdm-kesrcureadlock.md)

[**KeSrcuReadUnlock**](nf-wdm-kesrcureadunlock.md)

[**KeSrcuSynchronize**](nf-wdm-kesrcusynchronize.md)
