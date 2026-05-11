---
UID: NF:wdm.KeSrcuFree
tech.root: kernel
title: KeSrcuFree function (wdm.h)
ms.date: 09/02/2025
targetos: Windows
description: The KeSrcuFree routine performs cleanup of a Sleepable Read-Copy-Update (SRCU) partition and deallocates its storage.
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
 - KeSrcuFree
f1_keywords:
 - KeSrcuFree
 - wdm/KeSrcuFree
dev_langs:
 - c++
helpviewer_keywords:
 - KeSrcuFree
---

## -description

The **KeSrcuFree** routine performs cleanup of a Sleepable Read-Copy-Update (SRCU) partition and deallocates its storage.

## -parameters

### -param Rcu [in]

A pointer to the SRCU instance that was previously allocated by [**KeSrcuAllocate**](nf-wdm-kesrcuallocate.md).

## -remarks

**KeSrcuFree** performs cleanup and deallocates an SRCU partition that was previously created with [**KeSrcuAllocate**](nf-wdm-kesrcuallocate.md). This function ensures that all pending operations are completed before freeing the resources.

Don't access the SRCU instance after calling this function.

## -see-also

[**KeSrcuAllocate**](nf-wdm-kesrcuallocate.md)

[**KeSrcuReadLock**](nf-wdm-kesrcureadlock.md)

[**KeSrcuReadUnlock**](nf-wdm-kesrcureadunlock.md)

[**KeSrcuSynchronize**](nf-wdm-kesrcusynchronize.md)
