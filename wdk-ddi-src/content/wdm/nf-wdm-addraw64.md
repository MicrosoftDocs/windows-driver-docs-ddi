---
UID: NF:wdm.AddRaw64
tech.root: kernel
title: AddRaw64
ms.date: 08/28/2025
targetos: Windows
description: Performs a raw addition operation on a volatile LONG64 value without atomic guarantees.
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
 - AddRaw64
f1_keywords:
 - AddRaw64
 - wdm/AddRaw64
dev_langs:
 - c++
helpviewer_keywords:
 - AddRaw64
---

## -description

**AddRaw64** performs a raw addition operation on a volatile LONG64 value without atomic guarantees.

## -parameters

### -param Destination

[in, out] A pointer to the volatile LONG64 variable to modify. This parameter serves as both the source and destination for the addition operation.

### -param Value

[in] The LONG64 value to add to the destination.

## -returns

Returns the new LONG64 value after the addition operation.

## -remarks

The **AddRaw64** function performs a non-atomic read-add-write operation on 64-bit values. It reads the current value from the destination, adds the specified value, writes the result back, and returns the new value.

This function is not atomic and should not be used in multithreaded scenarios where multiple threads might access the same memory location. The operation consists of separate read and write operations that can be interrupted.

## -see-also

[AddRaw](nf-wdm-addraw.md)

[AddULong64Raw](nf-wdm-addulong64raw.md)

[ReadRaw64](nf-wdm-readraw64-r1.md)

[WriteRaw64](nf-wdm-writeraw64-r1.md)
