---
UID: NF:wdm.RtlFillDeviceMemory
tech.root: kernel
title: RtlFillDeviceMemory (wdm.h)
ms.date: 03/26/2024
targetos: Windows
description: Provides RtlFillVolatileMemory behavior in situations where the developer needs to additionally be sure that alignment faults won't be generated when accessing device memory.
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
 - RtlFillDeviceMemory
f1_keywords:
 - RtlFillDeviceMemory
 - wdm/RtlFillDeviceMemory
dev_langs:
 - c++
helpviewer_keywords:
 - RtlFillDeviceMemory
---

# RtlFillDeviceMemory function (wdm.h)

## -description

The **RtlFillDeviceMemory** function provides [**RtlFillVolatileMemory**](nf-wdm-rtlfillvolatilememory.md) behavior (for example, setting the contents of a buffer without interference from compiler optimizations) in situations where the developer needs to additionally be sure that alignment faults won't be generated when accessing device memory.

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

- The function isn't recognized as a compiler intrinsic so the compiler will never optimize away the call (either entirely or replace the call with an equivalent sequence of instructions). This differs from [**RtlFillMemory**](nf-wdm-rtlfillmemory.md) which is subject to various compiler optimizations.

- When the call is complete, the buffer has been overwritten with the desired value. This functions memory accesses to the *Destination* will only be performed within the function (for example, the compiler can't move memory accesses out of this function).

- The function may perform unaligned memory accesses only if the CPU supports unaligned memory accesses on device memory. If the CPU doesn't support unaligned device memory accesses, only aligned accesses will be performed.

- The function may access memory locations more than once as part of its operation.

> [!NOTE]
> This function only guarantees that the CPU's requirements for accessing memory mapped as device memory are respected. If a specific device has its own specific requirements for being accessed, this function should not be used (and instead, the developer must implement their own accessor functions). For example, this function makes no guarantee about the size of memory accesses generated (unless the CPU itself enforces these requirements).

> [!NOTE]
> This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the wdm.h header. You also need the library (volatileaccessk.lib) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

### Example

```cpp
// In this scenario we are setting data on memory mapped
// as "device memory" (for example, memory not backed by RAM). 
// On some platforms like ARM64, device memory cannot tolerate
// memory accesses that are not naturally aligned (for example, a 4-byte
// load must be 4-byte aligned). Functions like memset, RtlFillMemory,
// and even RtlFillVolatileMemory may perform unaligned memory accesses
// because it is typically faster to do this.
// To ensure only naturally aligned accesses happen, use RtlFillDeviceMemory.

RtlFillDeviceMemory(DeviceMemoryBuffer, 100, 0xAA);
```

## -see-also

[**RtlFillMemory**](nf-wdm-rtlfillmemory.md)

[**RtlFillVolatileMemory**](nf-wdm-rtlfillvolatilememory.md)
