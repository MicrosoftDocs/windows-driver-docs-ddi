---
UID: NF:wdm.RtlSetVolatileMemory
tech.root: kernel
title: RtlSetVolatileMemory (wdm.h)
ms.date: 07/14/2025
targetos: Windows
description: Provides RtlFillMemory behavior in situations where the developer needs to be sure that the setting operation occurs and returns a pointer to the filled memory.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll:
req.header: wdm.h
req.idl: 
req.include-header: Wdm.h
req.irql:
req.kmdf-ver: 
req.lib: volatileaccessk.lib (Kernel mode), volatileaccessu.lib (User mode)
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: See Remarks
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
 - RtlSetVolatileMemory
f1_keywords:
 - RtlSetVolatileMemory
 - wdm/RtlSetVolatileMemory
dev_langs:
 - c++
helpviewer_keywords:
 - RtlSetVolatileMemory
---

## -description

The **RtlSetVolatileMemory** function provides [**RtlFillMemory**](nf-wdm-rtlfillmemory.md) behavior (for example, setting the contents of a buffer) in situations where the developer needs to be sure that the setting operation occurs (for example, isn't subject to compiler optimizations). The function returns a pointer to the filled memory.

## -parameters

### -param Destination [out]

A pointer to the starting address of the block of memory to fill.

### -param Fill [in]

The byte value with which to fill the memory block.

### -param Length [in]

The size of the block of memory to fill, in bytes. This value must be less than the size of the **Destination** buffer.

## -returns

Returns a pointer to the filled memory block (*Destination*).

## -remarks

- The function isn't recognized as a compiler intrinsic so the compiler will never optimize away the call (either entirely or replace the call with an equivalent sequence of instructions). This differs from **RtlFillMemory** which is subject to various compiler optimizations.

- When the call returns, the buffer has been overwritten with the desired value. This function's memory accesses to the *Destination* will only be performed within the function (for example, the compiler can't move memory accesses out of this function).

- The function might perform unaligned memory accesses if the platform allows for it.

- The function might access memory locations more than once as part of its operation.

This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the wdm.h header. You also need the library (volatileaccessk.lib) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

### Example

```cpp
UCHAR SensitiveData[100];

// Imagine we temporarily store some sensitive cryptographic
// material in a buffer.

StoreCryptographicKey(&SensitiveData);

DoCryptographicOperation(&SensitiveData);

// Now that we are done using the sensitive data we want to
// erase it from the stack. We can use RtlSetVolatileMemory
// to fill the buffer and get a pointer to the filled memory.
// This call will not be optimized away by the compiler.

volatile VOID* clearedBuffer = RtlSetVolatileMemory(&SensitiveData, 0, sizeof(SensitiveData));
```

## -see-also

[**RtlFillMemory**](nf-wdm-rtlfillmemory.md)

[**RtlFillVolatileMemory**](nf-wdm-rtlfillvolatilememory.md)
