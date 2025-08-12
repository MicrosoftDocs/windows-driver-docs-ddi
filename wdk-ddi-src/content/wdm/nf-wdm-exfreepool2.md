---
UID: NF:wdm.ExFreePool2
tech.root: kernel
title: ExFreePool2 function (wdm.h)
ms.date: 08/12/2025
targetos: Windows
description: Frees a block of pool memory, optionally using secure pool extended parameters.
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
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
req.target-min-winverclnt: 
req.target-min-winversvr: Windows Server 2022
req.target-type: 
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
 - ExFreePool2
f1_keywords:
 - ExFreePool2
 - wdm/ExFreePool2
dev_langs:
 - c++
---

## -description

The **ExFreePool2** routine deallocates a previously allocated block of pool memory. It extends [**ExFreePool**](nf-wdm-exfreepool.md) by accepting optional extended parameters to free allocations associated with a secure pool created via [**ExCreatePool**](nf-wdm-excreatepool.md).

## -parameters

### -param P [in]

Pointer to the start of the allocation to free. Must be the exact address returned by the pool allocation routine such as [**ExAllocatePool2**](nf-wdm-exallocatepool2.md) or [**ExAllocatePool3**](nf-wdm-exallocatepool3.md). This parameter must not be NULL.

### -param Tag [in]

Pool tag originally supplied when the allocation was made.

### -param ExtendedParameters [in, optional]

Pointer to an array of extended parameter descriptors (type [**POOL_EXTENDED_PARAMETER**](ns-wdm-pool_extended_parameter.md)). See Remarks.

### -param ExtendedParametersCount [in]

Number of entries in the **ExtendedParameters** array. See Remarks.

## -remarks

The following table shows the requirements for using **ExFreePool2** with different types of allocations:

| Allocation Type      | ExtendedParametersCount | ExtendedParameters                             |
|----------------------|-------------------------|------------------------------------------------|
| Ordinary (non-secure)| 0                       | NULL                                           |
| Secure               | 1                       | Pointer to [**POOL_EXTENDED_PARAMS_SECURE_POOL**](ns-wdm-pool_extended_params_secure_pool.md) structure |

For secure pool frees, the associated **POOL_EXTENDED_PARAMS_SECURE_POOL** structure must:

* Contain a valid secure pool handle obtained from a successful allocation associated with a secure pool.
* Provide the correct cookie for the allocation being freed.
* Have all reserved fields (e.g., Buffer, SecurePoolFlags) set to NULL/0.
* Be the sole entry (ExtendedParametersCount == 1).

Validation failures (wrong count, unsupported parameter type, non-zero reserved fields, invalid handle, or secure kernel communication failure) cause a bug check (BAD_POOL_CALLER) rather than returning an error status.

This routine doesn't return an NTSTATUS value; it always completes the free or bug checks. A double free, corrupted header, tag mismatch, or freeing with incorrect secure pool metadata can also trigger pool integrity bug checks depending on system diagnostics.

**ExFreePool2** must be called at IRQL <= DISPATCH_LEVEL. If the allocation originated from paged pool the caller must be at IRQL <= APC_LEVEL. Secure pool allocations reside in nonpaged memory and can be freed at DISPATCH_LEVEL.

Use **ExFreePool2** for code that may free either standard or secure pool allocations to avoid branching on allocation origin.

## -see-also

[**ExFreePool**](nf-wdm-exfreepool.md)

[**ExFreePoolWithTag**](nf-wdm-exfreepoolwithtag.md)

[**ExAllocatePool2**](nf-wdm-exallocatepool2.md)

[**ExAllocatePool3**](nf-wdm-exallocatepool3.md)

[**ExCreatePool**](nf-wdm-excreatepool.md)
