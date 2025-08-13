---
UID: NF:usermode_accessors.ReadHandleFromMode
tech.root: kernel
title: ReadHandleFromMode
ms.date: 07/02/2025
targetos: Windows
description: The ReadHandleFromMode function safely reads a HANDLE value from memory based on the specified processor mode.
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
 - ReadHandleFromMode
f1_keywords:
 - ReadHandleFromMode
 - usermode_accessors/ReadHandleFromMode
dev_langs:
 - c++
helpviewer_keywords:
 - ReadHandleFromMode
ai-usage: ai-assisted
---

## -description

The **ReadHandleFromMode** function safely reads a HANDLE value from memory based on the specified processor mode.

## -parameters

### -param Source

[in] A pointer to the memory location from which to read the HANDLE value.

### -param Mode

[in] The processor mode that determines how the memory access is performed. **Mode** can be one of the following values.

| Value | Meaning |
| ----- | ------- |
| **KernelMode** | **Source** points to kernel-mode memory. The function performs a read from the specified address with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum). See Remarks for more details. |
| **UserMode** | **Source** points to user-mode memory. The function raises an exception if **Source** doesn't point to user-mode memory; otherwise it performs a read from the specified address with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum). See Remarks for more details. |

## -syntax

```cpp
FORCEINLINE
HANDLE
ReadHandleFromMode (
    _In_ const volatile HANDLE* Source,
    _In_ KPROCESSOR_MODE Mode
    );
```

## -returns

**ReadHandleFromMode** returns the HANDLE value read from the specified memory address.

## -remarks

This function provides a safe way to read a HANDLE value from memory, with extra safety checks when accessing user-mode memory. It ensures that the provided address is valid and accessible based on the specified processor mode.

This function doesn't enforce alignment.

It raises a structured exception if the memory access fails, such as when the source address is inaccessible or is invalid for the specified mode.

This function will never be optimized away by the compiler, nor will the compiler create additional accesses to this memory location before the function is called or after the function returns (unless the source code explicitly performs these accesses). The memory access is performed with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum).

This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**ReadHandleFromUser**](nf-usermode_accessors-readhandlefromuser.md)

[**WriteHandleToMode**](nf-usermode_accessors-writehandletomode.md)
