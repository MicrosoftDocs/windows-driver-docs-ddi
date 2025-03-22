---
UID: NF:wdm.RtlFillVolatileMemory
tech.root: kernel
title: RtlFillVolatileMemory (wdm.h)
ms.date: 03/26/2024
targetos: Windows
description: Provides RtlFillMemory behavior in situations where the developer needs to be sure that the setting operation occurs.
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
 - RtlFillVolatileMemory
f1_keywords:
 - RtlFillVolatileMemory
 - wdm/RtlFillVolatileMemory
dev_langs:
 - c++
helpviewer_keywords:
 - RtlFillVolatileMemory
---

# RtlFillVolatileMemory function (wdm.h)

## -description

The **RtlFillVolatileMemory** function provides [**RtlFillMemory**](nf-wdm-rtlfillmemory.md) behavior (for example, setting the contents of a buffer) in situations where the developer needs to be sure that the setting operation occurs (for example, isn't subject to compiler optimizations).

## -parameters

### -param Destination [out]

A pointer to the starting address of the block of memory to fill.

### -param Length [in]

The size of the block of memory to fill, in bytes. This value must be less than the size of the *Destination* buffer.

### -param Fill [in]

The byte value with which to fill the memory block.

## -returns

Returns the value of *Destination*.

## -remarks

- The function isn't recognized as a compiler intrinsic so the compiler will never optimize away the call (either entirely or replace the call with an equivalent sequence of instructions). This differs from **RtlFillMemory** which is subject to various compiler optimizations.

- When the call returns, the buffer has been overwritten with the desired value. This functions memory accesses to the *Destination* will only be performed within the function (for example, the compiler can't move memory accesses out of this function).

- The function may perform unaligned memory accesses if the platform allows for it.

- The function may access memory locations more than once as part of its operation.

> [!NOTE]
> This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the wdm.h header. You also need the library (volatileaccessk.lib) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

### Example

```cpp
UCHAR SensitiveData[100];

// Imagine we temporarily store some sensitive cryptographic
// material in a buffer.

StoreCryptographicKey(&SensitiveData);

DoCryptographicOperation(&SensitiveData);

// Now that we are done using the sensitive data we want to
// erase it from the stack. We cannot call RtlFillMemory because
// if the compiler realizes that "SensitiveData" is not
// referenced again the compiler can remove the call to RtlFillMemory.
// Instead we can call RtlSecureZeroMemory2, RtlZeroVolatileMemory, or RtlFillVolatileMemory
// (the former two are convenience wrappers around the latter). These
// calls will not be optimized away by the compiler.
// Note that RtlSecureZeroMemory2 performs better than
// RtlSecureZeroMemory function.

RtlFillVolatileMemory(&SensitiveData, sizeof(SensitiveData), 0);
```

## -see-also

[**RtlFillMemory**](nf-wdm-rtlfillmemory.md)
