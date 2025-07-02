---
UID: NF:usermode_accessors.CopyFromModeNonTemporal
tech.root: kernel
title: CopyFromModeNonTemporal
ms.date: 07/02/2025
targetos: Windows
description: The CopyFromModeNonTemporal function safely copies data from either kernel or user-mode memory to kernel memory using non-temporal instructions based on the specified processor mode.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: usermode_accessors.h
req.idl: 
req.include-header: 
req.irql: Less than or equal to APC_LEVEL
req.kmdf-ver: 
req.lib: umaccess.lib
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
 - usermode_accessors.h
api_name:
 - CopyFromModeNonTemporal
f1_keywords:
 - CopyFromModeNonTemporal
 - usermode_accessors/CopyFromModeNonTemporal
dev_langs:
 - c++
helpviewer_keywords:
 - CopyFromModeNonTemporal
---

## -description

The **CopyFromModeNonTemporal** function safely copies data from either kernel or user-mode memory to kernel memory using non-temporal instructions based on the specified processor mode.

## -parameters

### -param Destination

[out] A pointer to the kernel memory location where the data will be copied.

### -param Source

[in] A pointer to the memory location from which to copy the data.

### -param Length

[in] The number of bytes to copy.

### -param Mode

[in] The processor mode that determines how the memory access is performed. **Mode** can be one of the following values.

| Value | Meaning |
| ----- | ------- |
| **KernelMode** | **Source** points to kernel-mode memory. The function performs a direct memory copy using non-temporal instructions with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum). See Remarks for more details. |
| **UserMode** | **Source** points to user-mode memory. The function raises an exception if **Source** doesn't point to user-mode memory; otherwise it performs a copy from the specified address using non-temporal instructions with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum). See Remarks for more details. |

## -remarks

This function provides a safe way to copy data from either kernel or user-mode memory to kernel memory using non-temporal (streaming) instructions, with the copy mechanism determined by the specified processor mode. Non-temporal instructions can improve performance for large data transfers by bypassing the processor cache, reducing cache pollution.

When **Mode** is **KernelMode**, the function performs a direct memory copy using non-temporal instructions without additional safety checks. When **Mode** is **UserMode**, the function uses safe user-mode memory access with non-temporal instructions and validation.

This function is particularly useful when copying large amounts of data that are unlikely to be accessed again soon, as it avoids evicting other useful data from the cache.

The function validates that the destination pointer refers to kernel memory and raises a structured exception if the copy operation fails, such as when the source address is not valid for the specified mode or is inaccessible.

This function will never be optimized away by the compiler, nor will the compiler create additional accesses to this memory location before the function is called or after the function returns (unless the source code explicitly performs these accesses). The memory access is performed with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum).

This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**CopyFromMode**](nf-usermode_accessors-copyfrommode.md)

[**CopyFromUserNonTemporal**](nf-usermode_accessors-copyfromusernontemporal.md)

[**CopyToModeNonTemporal**](nf-usermode_accessors-copytomodenontemporal.md)
