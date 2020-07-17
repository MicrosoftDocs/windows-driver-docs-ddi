---
UID: NF:wdm.ExAllocatePool3
title: ExAllocatePool3
tech.root: kernel
ms.date: 05/12/2020
ms.topic: language-reference
targetos: Windows
description: 
req.assembly: 
req.construct-type: function
req.ddi-compliance: HwStorPortProhibitedDDIs, SpNoWait, StorPortStartIo
req.dll: NtosKrnl.exe
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.idl: 
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
 - ExAllocatePool3
f1_keywords:
 - wdm/ExAllocatePool3
 - ""
dev_langs:
 - c++
---

## -description

The **ExAllocatePool3** routine allocates pool memory of the specified type and returns a pointer to the allocated block. This routine is similar to **ExAllocatePool2** but it adds extended parameters.

## -parameters

### -param Flags

A ULONG64-typed value specifying the type of pool memory along with required and optional attributes. Multiple flag values can be combined using bit-wise OR. See [**POOL_FLAGS**](/windows-hardware/drivers/kernel/pool_flags) for possible values.

### -param NumberOfBytes

Specifies a non-zero number of bytes to allocate.

### -param Tag

The pool tag to use for the allocated memory. Specify the pool tag as a non-zero character literal of one to four characters delimited by single quotation marks (for example, `Tag1`). The string is usually specified in reverse order (for example, `1gaT`). Each ASCII character in the tag must be a value in the range 0x20 (space) to 0x7E (tilde). Each allocation code path should use a unique pool tag to help debuggers and verifiers identify the code path.

### -param ExtendedParameters

A pointer to an array of [**POOL_EXTENDED_PARAMETER**](ns-wdm-pool_extended_parameter.md) structures that specify additional attributes for the allocation.

### -param ExtendedParametersCount

A ULONG value specifying the number of parameters in **ExtendedParameters**.

## -returns

**ExAllocatePool3** returns a pointer to the allocated memory.

The following conditions cause the function to return NULL by default. If **POOL_FLAG_RAISE_ON_FAILURE** is specified, the function raises an exception.

* Insufficient memory
* **Tag** is set to 0 or invalid POOL_FLAGS are specified
* Invalid **POOL_EXTENDED_PARAMETER** structures

## -remarks

If you are building a driver that targets versions of Windows prior to Windows 10, version 2004, use [**ExAllocatePoolPriorityZero**](nf-wdm-exallocatepoolpriorityzero.md) or [**ExAllocatePoolPriorityUninitialized**](nf-wdm-exallocatepoolpriorityuninitialized.md).

See the remarks of [**ExAllocatePool2**](/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepool2) for additional information.

## -see-also

[**ExAllocatePool2**](nf-wdm-exallocatepool2.md)
