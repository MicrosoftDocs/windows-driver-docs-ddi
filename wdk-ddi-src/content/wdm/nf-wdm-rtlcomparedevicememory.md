---
UID: NF:wdm.RtlCompareDeviceMemory
tech.root: kernel
title: RtlCompareDeviceMemory (wdm.h)
ms.date: 07/14/2025
targetos: Windows
description: Compares two blocks of device memory and returns the number of bytes that match until the first difference.
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
 - RtlCompareDeviceMemory
f1_keywords:
 - RtlCompareDeviceMemory
 - wdm/RtlCompareDeviceMemory
dev_langs:
 - c++
helpviewer_keywords:
 - RtlCompareDeviceMemory
---

## -description

The **RtlCompareDeviceMemory** function compares two blocks of device memory and returns the number of bytes that match until the first difference. This function is safe for use on device memory because it uses byte-level accesses that are guaranteed to be performed as specified.

## -parameters

### -param Source1 [in]

A pointer to the first block of memory to compare.

### -param Source2 [in]

A pointer to the second block of memory to compare.

### -param Length [in]

The number of bytes to compare.

## -returns

**RtlCompareDeviceMemory** returns the number of bytes in the two blocks that match. If all bytes match up to the specified **Length** value, the **Length** value is returned.

## -remarks

- The function isn't recognized as a compiler intrinsic so the compiler will never optimize away the call (either entirely or replace the call with an equivalent sequence of instructions). This differs from [**RtlCompareMemory**](nf-wdm-rtlcomparememory.md) which is subject to various compiler optimizations.

- The function uses byte-level accesses to ensure proper handling of device memory that may have side effects or special access requirements.

- The routine starts by comparing the first byte in the first block to the first byte in the second block, and continues to compare successive bytes in the two blocks while the bytes match. The routine stops comparing bytes when it encounters the first pair of bytes that are not equal, or when the number of matching bytes equals the **Length** parameter value, whichever occurs first.

- The function might perform unaligned memory accesses if the platform allows for it.

This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the wdm.h header. You also need the library (volatileaccessk.lib) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

### Example

```cpp
UCHAR DeviceBuffer1[256];
UCHAR DeviceBuffer2[256];

// Read data from device memory into buffers
ReadFromDevice(DeviceBuffer1, sizeof(DeviceBuffer1));
ReadFromDevice(DeviceBuffer2, sizeof(DeviceBuffer2));

// Compare the device memory buffers
size_t matchingBytes = RtlCompareDeviceMemory(DeviceBuffer1, DeviceBuffer2, sizeof(DeviceBuffer1));

if (matchingBytes == sizeof(DeviceBuffer1)) {
    // All bytes matched
    DbgPrint("Device buffers are identical\n");
} else {
    // Difference found at byte offset 'matchingBytes'
    DbgPrint("Device buffers differ starting at byte %zu\n", matchingBytes);
}
```

## -see-also

[**RtlCompareMemory**](nf-wdm-rtlcomparememory.md)

[**RtlFillVolatileMemory**](nf-wdm-rtlfillvolatilememory.md)
