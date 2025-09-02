---
UID: NF:wdm.AddULongRaw
tech.root: kernel
title: AddULongRaw
ms.date: 08/28/2025
targetos: Windows
description: Performs a raw addition operation on a volatile ULONG value without atomic guarantees.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: Any level
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
 - AddULongRaw
f1_keywords:
 - AddULongRaw
 - wdm/AddULongRaw
dev_langs:
 - c++
helpviewer_keywords:
 - AddULongRaw
---

## -description

**AddULongRaw** performs a raw addition operation on a volatile ULONG value without atomic guarantees.

## -parameters

### -param Destination

[in, out] A pointer to the volatile ULONG variable to modify. This parameter serves as both the source and destination for the addition operation.

### -param Value

[in] The ULONG value to add to the destination.

## -returns

Returns the new ULONG value after the addition operation.

## -remarks

The **AddULongRaw** function performs a non-atomic read-add-write operation on unsigned long values. This function internally casts the ULONG pointers to LONG pointers and calls `AddRaw`, then casts the result back to ULONG.

This function is not atomic and should not be used in multithreaded scenarios where multiple threads might access the same memory location. The operation consists of separate read and write operations that can be interrupted.

## -see-also

[AddRaw](nf-wdm-addraw.md)

[AddULong64Raw](nf-wdm-addulong64raw.md)

[AddRaw64](nf-wdm-addraw64.md)
