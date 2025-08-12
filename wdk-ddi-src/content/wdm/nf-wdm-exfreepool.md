---
UID: NF:wdm.ExFreePool
title: ExFreePool function (wdm.h)
description: The ExFreePool function (wdm.h) deallocates a specified block of pool memory that was previously allocated.
tech.root: kernel
ms.date: 08/12/2025
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows 2000
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: DoubleExFreePool
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - ExFreePool
 - wdm/ExFreePool
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ExFreePool
---

## -description

The **ExFreePool** routine deallocates a block of pool memory.

## -parameters

### -param P [in]

Specifies the address of the block of pool memory being deallocated.

## -remarks

This routine releases memory allocated by [**ExAllocatePool**](nf-wdm-exallocatepool.md), [**ExAllocatePoolWithTag**](nf-wdm-exallocatepoolwithtag.md), [**ExAllocatePoolWithQuota**](nf-wdm-exallocatepoolwithquota.md), or [**ExAllocatePoolWithQuotaTag**](nf-wdm-exallocatepoolwithquotatag.md). The memory block must not be accessed after it is freed.

Drivers can also use the [**ExFreePoolWithTag**](nf-wdm-exfreepoolwithtag.md) routine to free buffers allocated by [**ExAllocatePoolWithTag**](nf-wdm-exallocatepoolwithtag.md) and [**ExAllocatePoolWithQuotaTag**](nf-wdm-exallocatepoolwithquotatag.md).

Callers of **ExFreePool** must be running at IRQL <= DISPATCH_LEVEL. A caller at DISPATCH_LEVEL must have specified a NonPagedXxxPoolType when the memory was allocated. Otherwise, the caller must be running at IRQL <= APC_LEVEL.

## -see-also

[**ExAllocatePool**](nf-wdm-exallocatepool.md)

[**ExAllocatePoolWithQuota**](nf-wdm-exallocatepoolwithquota.md)

[**ExAllocatePoolWithQuotaTag**](nf-wdm-exallocatepoolwithquotatag.md)

[**ExAllocatePoolWithTag**](nf-wdm-exallocatepoolwithtag.md)

[**ExFreePoolWithTag**](nf-wdm-exfreepoolwithtag.md)
