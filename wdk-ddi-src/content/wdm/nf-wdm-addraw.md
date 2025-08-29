---
UID: NF:wdm.AddRaw
tech.root: kernel
title: AddRaw
ms.date: 08/28/2025
targetos: Windows
description: Performs a raw addition operation on a volatile LONG value without atomic guarantees.
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
 - AddRaw
f1_keywords:
 - AddRaw
 - wdm/AddRaw
dev_langs:
 - c++
helpviewer_keywords:
 - AddRaw
---

## -description

**AddRaw** performs a raw addition operation on a volatile LONG value without atomic guarantees.

## -parameters

### -param Destination

[in, out] A pointer to a volatile LONG variable to modify. This parameter serves as both the source and destination for the addition operation.

### -param Value

[in] The LONG value to add to the destination.

## -returns

Returns the new LONG value after the addition operation.

## -remarks

The **AddRaw** function performs a non-atomic read-add-write operation. It reads the current value from the destination, adds the specified value, writes the result back, and returns the new value.

This function is not atomic and should not be used in multithreaded scenarios where multiple reads might access the same memory location. The operation consists of separate read and write operations that can be interrupted.

## -see-also

[AddRaw64](nf-wdm-addraw64.md)

[AddULongRaw](nf-wdm-addulongraw.md)

[ReadRaw](nf-wdm-readraw~r1.md)

[WriteRaw](nf-wdm-writeraw~r1.md)
