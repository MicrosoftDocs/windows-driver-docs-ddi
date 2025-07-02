---
UID: NF:usermode_accessors.CopyFromModeAligned
tech.root: kernel
title: CopyFromModeAligned
ms.date: 06/24/2025
targetos: Windows
description: The CopyFromModeAligned macro safely copies data from specified-mode memory to kernel memory, with alignment checking.
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
 - CopyFromModeAligned
f1_keywords:
 - CopyFromModeAligned
 - usermode_accessors/CopyFromModeAligned
dev_langs:
 - c++
helpviewer_keywords:
 - CopyFromModeAligned
---

## -description

The **CopyFromModeAligned** macro safely copies data from specified-mode memory to kernel memory, with alignment checking.

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
| **KernelMode** | **Source** points to kernel-mode memory. The function performs a direct memory copy with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum). See Remarks for more details. |
| **UserMode** | **Source** points to user-mode memory. The function raises an exception if **Source** doesn't point to user-mode memory; otherwise it performs a copy from the specified address with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum). See Remarks for more details. |

### -param Alignment

[in] The alignment boundary that the source pointer must satisfy.

## -remarks

This macro provides a safe way to copy data from either kernel or user-mode memory to kernel memory, with the copy mechanism determined by the specified processor mode and alignment verification.

When Mode is UserMode, the macro first checks that the source pointer meets the specified alignment requirements before performing the copy. When Mode is KernelMode, no alignment checking is performed.

The macro validates that the destination pointer refers to kernel memory and raises a structured exception if the copy operation fails, such as when the source address is not valid for the specified mode, is inaccessible, or (for UserMode) doesn't meet the alignment requirements.

This macro will never be optimized away by the compiler, nor will the compiler create additional accesses to this memory location before the macro is called or after the macro returns (unless the source code explicitly performs these accesses). The memory access is performed with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum).

This macro works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the macro definition from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**CopyFromMode**](nf-usermode_accessors-copyfrommode.md)

[**CopyFromUser**](nf-usermode_accessors-copyfromuser.md)

[**CopyFromUserAligned**](nf-usermode_accessors-copyfromuseraligned.md)

[**CopyFromModeNonTemporal**](nf-usermode_accessors-copyfrommodenontemporal.md)

[**CopyToMode**](nf-usermode_accessors-copytomode.md)
