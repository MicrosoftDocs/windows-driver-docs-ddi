---
UID: NF:usermode_accessors.CopyFromModeAligned
tech.root: kernel
title: CopyFromModeAligned
ms.date: 07/02/2025
targetos: Windows
description: The CopyFromModeAligned macro safely copies data from specified-mode memory to kernel memory, with alignment checking.
prerelease: false
req.assembly: 
req.construct-type: macro
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
| **KernelMode** | **Source** points to kernel-mode memory. The macro performs a direct memory copy with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum). |
| **UserMode** | **Source** points to user-mode memory. The macro raises an exception if **Source** doesn't point to user-mode memory; otherwise it performs a copy from the specified address with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum). |

### -param Alignment

[in] The alignment boundary that the source pointer must satisfy.

## -remarks

This macro provides a safe way to copy data from either kernel or user-mode memory to kernel memory, with the copy mechanism determined by the specified processor mode and alignment verification. This allows for flexible memory operations that can adapt to different execution contexts while ensuring proper alignment requirements.

When **Mode** is **KernelMode**:

* The macro performs a volatile copy using [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum).

* The macro isn't recognized as a compiler intrinsic so the compiler will never optimize away the call (either entirely or replace the call with an equivalent sequence of instructions).

* When the call returns, the data has been copied from **Source** to **Destination**. This macro's memory accesses to the **Source** and **Destination** will only be performed within the function (for example, the compiler can't move memory accesses out of this function).

* The macro might access memory locations more than once as part of its copy operation.

* The macro doesn't support copy operations when **Source** and **Destination** overlap each other.

The macro raises a structured exception if the copy operation fails, such as when the source address is not valid for the specified mode, is not properly aligned according to the **Alignment** parameter, or is inaccessible.

This macro will never be optimized away by the compiler, nor will the compiler create additional accesses to this memory location before the macro is called or after the macro returns (unless the source code explicitly performs these accesses).

This macro works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**CopyFromMode**](nf-usermode_accessors-copyfrommode.md)

[**CopyFromUser**](nf-usermode_accessors-copyfromuser.md)

[**CopyFromUserAligned**](nf-usermode_accessors-copyfromuseraligned.md)

[**CopyFromModeNonTemporal**](nf-usermode_accessors-copyfrommodenontemporal.md)

[**CopyToMode**](nf-usermode_accessors-copytomode.md)
