---
UID: NF:wdm.KeRcuSynchronize
tech.root: kernel
title: KeRcuSynchronize function (wdm.h)
ms.date: 09/02/2025
targetos: Windows
description: The KeRcuSynchronize function waits for a grace period to elapse in the default RCU domain, ensuring all pre-existing RCU read-side critical sections have completed.
prerelease: false
ai-usage: ai-assisted
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: Wdm.h
req.irql: <= APC_LEVEL
req.kmdf-ver: 
req.lib: NtosKrnl.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: Windows Server 2025
req.target-type: Universal
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - KeRcuSynchronize
f1_keywords:
 - KeRcuSynchronize
 - wdm/KeRcuSynchronize
dev_langs:
 - c++
helpviewer_keywords:
 - KeRcuSynchronize
---

## -description

The **KeRcuSynchronize** function waits for a grace period to elapse in the default RCU (Read-Copy-Update) domain, ensuring that all pre-existing RCU read-side critical sections have completed.

## -remarks

**KeRcuSynchronize** is a blocking operation that waits for a grace period using a kernel gate object. It must be called at IRQL < DISPATCH_LEVEL (typically PASSIVE_LEVEL) because it can cause the calling thread to be suspended.

This function blocks the calling thread until all RCU read-side critical sections that were active at the time of the call have exited. It provides a synchronization point for writers to safely reclaim or modify RCU-protected data structures.

**KeRcuSynchronize** guarantees that:

- All RCU read-side critical sections that began before the call to **KeRcuSynchronize** will complete before the function returns.
- It's safe to reclaim memory or data structures protected by RCU after this function returns.
- New readers that begin after **KeRcuSynchronize** starts may or may not be waited for.

This function is typically used in update-side code paths where the caller needs to ensure that all readers have finished accessing data structures before safely reclaiming or modifying them.

The function is non-failing. It will always complete successfully and cannot return an error.

For more complex scenarios requiring custom synchronization domains, use [**KeSrcuSynchronize**](nf-wdm-kesrcusynchronize.md) with an explicit SRCU partition.

## -see-also

[**KeRcuReadLock**](nf-wdm-kercureadlock.md)

[**KeRcuReadUnlock**](nf-wdm-kercureadunlock.md)

[**KeSrcuSynchronize**](nf-wdm-kesrcusynchronize.md)

[**KeSrcuAllocate**](nf-wdm-kesrcuallocate.md)

[**KeSrcuFree**](nf-wdm-kesrcufree.md)
