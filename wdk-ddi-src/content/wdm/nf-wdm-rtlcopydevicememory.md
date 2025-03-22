---
UID: NF:wdm.RtlCopyDeviceMemory
tech.root: kernel
title: RtlCopyDeviceMemory (wdm.h)
ms.date: 03/26/2024
targetos: Windows
description: Provides RtlCopyVolatileMemory behavior in situations where the developer needs to additionally be sure that alignment faults won't be generated when accessing device memory.
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
 - RtlCopyDeviceMemory
f1_keywords:
 - RtlCopyDeviceMemory
 - wdm/RtlCopyDeviceMemory
dev_langs:
 - c++
helpviewer_keywords:
 - RtlCopyDeviceMemory
---

# RtlCopyDeviceMemory function (wdm.h)

## -description

The **RtlCopyDeviceMemory** function provides [**RtlCopyVolatileMemory**](nf-wdm-rtlcopyvolatilememory.md) behavior (for example, copying memory from one location to another without interference from compiler optimizations) in situations where the developer needs to additionally be sure that alignment faults won't be generated when accessing device memory.

## -parameters

### -param Destination [out]

A pointer to the starting address of the copied block's destination.

### -param Source [in]

A pointer to the starting address of the block of memory to copy.

### -param Length [in]

The size of the block of memory to copy, in bytes.

## -returns

Returns the value of *Destination*.

## -remarks

The **RtlCopyDeviceMemory** function has the following properties:

- The function isn't recognized as a compiler intrinsic so the compiler will never optimize away the call (either entirely, or replace the call with an equivalent sequence of instructions). This differs from [**RtlCopyMemory**](nf-wdm-rtlcopymemory.md) which is subject to various compiler optimizations.

- When the call returns, the data has been copied from Source to Destination. This functions memory accesses to the *Source* and *Destination* will only be performed within the function (for example, the compiler can't move memory accesses out of this function).

- The function may perform unaligned memory accesses only if the CPU supports unaligned memory accesses on device memory. If the CPU doesn't support unaligned device memory accesses, only aligned accesses will be performed.

- The function may access memory locations more than once as part of its copy operation.

- Doesn't support copy operations when *Source* and *Destination* overlap each other. If overlapping buffers are provided, fast-fails with the error code FAST_FAIL_INVALID_ARG.

> [!NOTE]
> This function only guarantees that the CPU's requirements for accessing memory mapped as device memory are respected. If a specific device has its own specific requirements for being accessed, this function should not be used (and instead, the developer must implement their own accessor functions). For example, this function makes no guarantee about the size of memory accesses generated (unless the CPU itself enforces these requirements).

> [!NOTE]
> This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the wdm.h header. You also need the library (volatileaccessk.lib) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

### Example

```cpp
UCHAR* CopyBuffer;

// In this scenario we are copying data from memory mapped
// as "device memory" (for example, memory not backed by RAM). On
// some platforms like ARM64, device memory cannot tolerate
// memory accesses that are not naturally aligned (for example, a 4-byte
// load must be 4-byte aligned). Functions like memcpy, RtlCopyMemory,
// and even RtlCopyVolatileMemory may perform unaligned memory accesses
// because it is typically faster to do this.
// To ensure only naturally aligned accesses happen, use RtlCopyDeviceMemory.

RtlCopyDeviceMemory(CopyBuffer, DeviceMemoryBuffer, 100);
```

## -see-also

[**RtlCopyMemory**](nf-wdm-rtlcopymemory.md)

[**RtlCopyVolatileMemory**](nf-wdm-rtlcopyvolatilememory.md)
