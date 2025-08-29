---
UID: NF:wdm.AddULong64Raw
tech.root: kernel
title: AddULong64Raw
ms.date: 08/28/2025
targetos: Windows
description: Performs a raw addition operation on a volatile ULONG64 value without atomic guarantees.
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
 - AddULong64Raw
f1_keywords:
 - AddULong64Raw
 - wdm/AddULong64Raw
dev_langs:
 - c++
helpviewer_keywords:
 - AddULong64Raw
---

## -description

**AddULong64Raw** performs a raw addition operation on a volatile ULONG64 value without atomic guarantees.

## -parameters

### -param Destination

[in, out] A pointer to the volatile ULONG64 variable to modify. This parameter serves as both the source and destination for the addition operation.

### -param Value

[in] The ULONG64 value to add to the destination.

## -returns

Returns the new ULONG64 value after the addition operation.

## -remarks

The **AddULong64Raw** function performs a non-atomic read-add-write operation on 64-bit unsigned long values.

This function shouldn't be used in multithreaded scenarios where multiple threads might access the same memory location. The operation consists of separate read and write operations that can be interrupted.

## -see-also

[AddRaw64](nf-wdm-addraw64.md)

[AddULongRaw](nf-wdm-addulongraw.md)

[AddRaw](nf-wdm-addraw.md)

[ReadULong64Raw](nf-wdm-readulong64raw.md)

[WriteULong64Raw](nf-wdm-writeulong64raw.md)
