---
UID: NF:usermode_accessors.WriteStructToMode
tech.root: kernel
title: WriteStructToMode
ms.date: 07/02/2025
targetos: Windows
description: The WriteStructToMode macro safely writes a structure to memory based on the specified processor mode.
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
 - WriteStructToMode
f1_keywords:
 - WriteStructToMode
 - usermode_accessors/WriteStructToMode
dev_langs:
 - c++
helpviewer_keywords:
 - WriteStructToMode
---

## -description

The **WriteStructToMode** macro safely writes a structure to memory based on the specified processor mode.

## -parameters

### -param Destination

[out] A pointer to the memory location where the structure will be written.

### -param Source

[in] A pointer to the structure to write to the destination memory location.

### -param Mode

[in] The processor mode that determines how the memory access is performed. **Mode** can be one of the following values.

| Value | Meaning |
| ----- | ------- |
| **KernelMode** | **Destination** points to kernel-mode memory. The macro performs a write to the specified address with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum). See Remarks for more details. |
| **UserMode** | **Destination** points to user-mode memory. The macro raises an exception if **Destination** doesn't point to user-mode memory; otherwise it performs a write to the specified address with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum). See Remarks for more details. |

## -remarks

This macro provides a safe way to write a structure to memory, with extra safety checks when accessing user-mode memory. It ensures that the provided address is valid and accessible based on the specified processor mode.

The macro validates that **Source** and **Destination** point to compatible types and automatically determines the structure size for the copy operation.

This macro doesn't enforce alignment.

It raises a structured exception if the memory access fails, such as when the destination address isn't valid or is inaccessible for the specified processor mode.

This macro will never be optimized away by the compiler, nor will the compiler create additional accesses to this memory location before the macro is called or after the macro returns (unless the source code explicitly performs these accesses). The memory access is performed with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum).

This macro works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the macro declaration from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**WriteStructToModeHelper**](nf-usermode_accessors-writestructtomodehelper.md)

[**WriteStructToUser**](nf-usermode_accessors-writestructtouser.md)

[**ReadStructFromMode**](nf-usermode_accessors-readstructfrommode.md)
