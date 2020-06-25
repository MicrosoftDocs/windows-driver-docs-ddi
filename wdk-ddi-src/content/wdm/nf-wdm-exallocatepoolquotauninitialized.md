---
UID: NF:wdm.ExAllocatePoolQuotaUninitialized
title: ExAllocatePoolQuotaUninitialized
tech.root: kernel
ms.date: 03/01/2020
ms.topic: language-reference
targetos: Windows
description: 
req.assembly: 
req.construct-type: function
req.ddi-compliance: HwStorPortProhibitedDDIs, SpNoWait, StorPortStartIo 
req.dll: NtosKrnl.exe
req.header: wdm.h
req.idl: 
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.irql: <= DISPATCH_LEVEL (see Remarks section)
req.kmdf-ver: 
req.lib: NtosKrnl.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 2004
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
 - wdm.h
api_name:
 - ExAllocatePoolQuotaUninitialized
f1_keywords:
 - wdm/ExAllocatePoolQuotaUninitialized
dev_langs:
 - c++
---

## -description

This routine is a wrapper and replacement option for [**ExAllocatePoolWithQuotaTag**](nf-wdm-exallocatepoolwithquotatag.md). There is no difference in functionality.

The **ExAllocatePoolQuotaUninitialized** routine allocates pool memory, charging the quota against the current process. 

## -parameters

### -param PoolType

The type of pool memory to allocate. For a description of the available pool memory types, see [**POOL_TYPE**](ne-wdm-_pool_type.md). 

Similarly, you can modify the *PoolType* value by bitwise-ORing this value with the **POOL_COLD_ALLOCATION** flag (also defined in `wdm.h`) as a hint to the kernel to allocate the memory from pages that are likely to be paged out quickly. To reduce the amount of resident pool memory as much as possible, you should not reference these allocations frequently. The **POOL_COLD_ALLOCATION** flag is only advisory. 


### -param NumberOfBytes

The number of bytes to allocate. 


### -param Tag

The pool tag to use for the allocated memory. Specify the pool tag as a non-zero character literal of one to four characters delimited by single quotation marks (for example, `Tag1`). The string is usually specified in reverse order (for example, `1gaT`). Each ASCII character in the tag must be a value in the range 0x20 (space) to 0x7E (tilde). Each allocation code path should use a unique pool tag to help debuggers and verifiers identify the code path. 

## -returns

**ExAllocatePoolQuotaUninitialized** returns a pointer to the allocated pool. 

If the request cannot be satisfied, **ExAllocatePoolQuotaUninitialized** raises an exception unless POOL_QUOTA_FAIL_INSTEAD_OF_RAISE is specified. Using POOL_QUOTA_FAIL_INSTEAD_OF_RAISE is preferred for performance reasons. 

## -remarks

This routine is called by highest-level drivers that allocate memory to satisfy a request in the context of the process that originally made the I/O request. Lower-level drivers call [**ExAllocatePoolUninitialized**](nf-wdm-exallocatepooluninitialized.md) instead. 

> [!NOTE]
> Memory that **ExAllocatePoolQuotaUninitialized** allocates is uninitialized. A kernel-mode driver must first zero this memory if it is going to make it visible to user-mode software (to avoid leaking potentially privileged contents)

See the Remarks section of [**ExAllocatePoolWithQuotaTag**](nf-wdm-exallocatepoolwithquotatag.md) for additional guidance.


## -see-also

* [**ExAllocatePoolQuotaZero**](nf-wdm-exallocatepoolquotazero.md)
* [**ExAllocatePoolWithQuotaTag**](nf-wdm-exallocatepoolwithquotatag.md)
