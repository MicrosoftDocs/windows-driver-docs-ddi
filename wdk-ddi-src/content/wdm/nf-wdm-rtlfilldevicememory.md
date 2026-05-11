---
UID: NF:wdm.RtlFillDeviceMemory
tech.root: kernel
title: RtlFillDeviceMemory function (wdm.h)
ms.date: 07/14/2025
targetos: Windows
description: The RtlFillDeviceMemory routine fills a block of device memory with the specified fill value and returns a pointer to the filled memory.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: NtosKrnl.exe
req.header: wdm.h
req.idl: 
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.irql: Any level (see Remarks section)
req.kmdf-ver: 
req.lib: volatileaccessk.lib (Kernel mode), volatileaccessu.lib (User mode)
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt:
req.target-min-winversvr: 
req.target-type: Universal
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
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

## -description

The **RtlFillDeviceMemory** routine fills a block of device memory with the specified fill value and returns a pointer to the filled memory. This function is safe for use on device memory because it uses appropriate access patterns for device memory regions.

## -parameters

### -param Destination [out]

A pointer to the starting address of the volatile device memory block to fill.

### -param Length [in]

The size of the block of memory to fill, in bytes. This value must be less than or equal to the size of the **Destination** buffer.

### -param Fill [in]

The byte value with which to fill the memory block.

## -returns

**RtlFillDeviceMemory** returns a pointer to the filled volatile device memory block (**Destination**).

## -remarks

The **RtlFillDeviceMemory** routine is designed for safe filling of device memory regions where standard memory filling functions might not be appropriate due to the special characteristics of device memory.

- The function uses volatile memory accesses to ensure proper handling of device memory that may have side effects or special access requirements.

- The function is optimized for performance while maintaining safety for device memory access patterns.

- The function might perform unaligned memory accesses if the platform allows for it.

- The function might use optimized filling patterns for larger memory blocks while ensuring device memory safety.

This function provides [**RtlFillMemory**](nf-wdm-rtlfillmemory.md) behavior specifically designed for device memory regions.

Callers of **RtlFillDeviceMemory** can be running at any IRQL if the destination memory block is in nonpaged system memory. Otherwise, the caller must be running at IRQL <= APC_LEVEL.

This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the wdm.h header. You also need the library (volatileaccessk.lib) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

### Example

```cpp
volatile UCHAR* DeviceBuffer;
SIZE_T BufferSize = 1024;

// Allocate or map device memory
DeviceBuffer = MapDeviceMemory(BufferSize);

// Fill the device memory with a specific pattern
volatile void* result = RtlFillDeviceMemory(DeviceBuffer, BufferSize, 0xAA);

// Use the filled device memory
ProcessDeviceData(DeviceBuffer, BufferSize);

// Clean up
UnmapDeviceMemory(DeviceBuffer);
```

## -see-also

[**RtlFillMemory**](nf-wdm-rtlfillmemory.md)

[**RtlSetVolatileMemory**](nf-wdm-rtlsetvolatilememory.md)

[**RtlCompareDeviceMemory**](nf-wdm-rtlcomparedevicememory.md)

[**RtlEqualDeviceMemory**](nf-wdm-rtlequaldevicememory.md)
