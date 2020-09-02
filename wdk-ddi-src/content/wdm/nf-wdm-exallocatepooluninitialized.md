---
UID: NF:wdm.ExAllocatePoolUninitialized
title: ExAllocatePoolUninitialized
tech.root: kernel
ms.date: 03/01/2020
ms.topic: language-reference
targetos: Windows
description: 
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.irql: <= DISPATCH_LEVEL (see Remarks section)
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Requires WDK for Windows 10, version 2004. Targets Windows 7 and later versions of the Windows operating system.
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
 - ExAllocatePoolUninitialized
f1_keywords:
 - ExAllocatePoolUninitialized
 - wdm/ExAllocatePoolUninitialized
dev_langs:
 - c++
---

## -description

This routine is a wrapper and replacement option for [**ExAllocatePoolWithTag**](nf-wdm-exallocatepoolwithtag.md).

* To support Windows versions earlier than Windows 10, version 2004, use [**ExAllocatePoolUninitialized**](nf-wdm-exallocatepooluninitialized.md) or [**ExAllocatePoolZero**](nf-wdm-exallocatepoolzero.md).
* To support Windows 10, version 2004 and later, use [**ExAllocatePool2**](nf-wdm-exallocatepool2.md).

## -parameters

### -param PoolType

### -param NumberOfBytes

### -param Tag

## -returns

## -remarks

Use this wrapper if you want to explicitly not zero the allocated memory range.

A driver should only access memory within the byte range that it allocates.  Accessing memory outside this range may corrupt the pool and cause the system to crash. 

> [!NOTE]
> Memory that **ExAllocatePoolUninitialized** allocates is uninitialized. A kernel-mode driver must first zero this memory if it is going to make it visible to user-mode software (to avoid leaking potentially privileged contents). 

See the Remarks section of [**ExAllocatePoolWithTag**](nf-wdm-exallocatepoolwithtag.md) for additional guidance.

## -see-also

[**ExAllocatePoolZero**](nf-wdm-exallocatepoolzero.md)

