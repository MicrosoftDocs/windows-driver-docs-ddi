---
UID: NF:wdm.RtlZeroDeviceMemory
tech.root: kernel
title: RtlZeroDeviceMemory (wdm.h)
ms.date: 03/26/2024
targetos: Windows
description: Provides a convenience wrapper around RtlFillDeviceMemory.
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
 - RtlZeroDeviceMemory
f1_keywords:
 - RtlZeroDeviceMemory
 - wdm/RtlZeroDeviceMemory
dev_langs:
 - c++
helpviewer_keywords:
 - RtlZeroDeviceMemory
---

# RtlZeroDeviceMemory function (wdm.h)

## -description

The **RtlZeroDeviceMemory** function is a convenience wrapper around [**RtlFillDeviceMemory**](nf-wdm-rtlfilldevicememory.md).

## -parameters

### -param Destination [out]

A pointer to the starting address of the block of memory to fill with zeros.

### -param Length [in]

The size of the block of memory to fill with zeros, in bytes.

## -returns

Returns the value of *Destination*.

## -remarks

The **RtlZeroDeviceMemory** function is a convenience wrapper around **RtlFillDeviceMemory**.

For more information, see the remarks section of [**RtlFillDeviceMemory**](nf-wdm-rtlfilldevicememory.md).

> [!NOTE]
> This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the wdm.h header. You also need the library (volatileaccessk.lib) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

### Example

```cpp
// In this scenario we are setting data on memory mapped
// as "device memory" (for example, memory not backed by RAM) to the value zero. On
// some platforms like ARM64, device memory cannot tolerate
// memory accesses that are not naturally aligned (for example, a 4-byte
// load must be 4-byte aligned). Functions like memset, RtlFillMemory,
// and even RtlFillVolatileMemory may perform unaligned memory accesses
// because it is typically faster to do this.
// To ensure only naturally aligned accesses happen, use RtlFillDeviceMemory.
//
// RtlZeroDeviceMemory is an wrapper around RtlFillDeviceMemory that sets the memory
// to zero.

RtlZeroDeviceMemory(DeviceMemoryBuffer, 100);
```

## -see-also

[**RtlFillDeviceMemory**](nf-wdm-rtlfilldevicememory.md)
