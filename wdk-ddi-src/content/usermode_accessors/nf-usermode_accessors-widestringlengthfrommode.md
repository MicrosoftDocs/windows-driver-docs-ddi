---
UID: NF:usermode_accessors.WideStringLengthFromMode
tech.root: kernel
title: WideStringLengthFromMode
ms.date: 07/02/2025
targetos: Windows
description: The WideStringLengthFromMode function calculates the length of a null-terminated wide character string, based on the specified processor mode.
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
 - WideStringLengthFromMode
f1_keywords:
 - WideStringLengthFromMode
 - usermode_accessors/WideStringLengthFromMode
dev_langs:
 - c++
helpviewer_keywords:
 - WideStringLengthFromMode
ai-usage: ai-assisted
---

## -description

The **WideStringLengthFromMode** function calculates the length of a null-terminated wide character string, based on the specified processor mode.

## -parameters

### -param String

[in] A pointer to a null-terminated wide character string.

### -param Mode

[in] The processor mode that determines how the memory access is performed. **Mode** can be one of the following values.

| Value | Meaning |
| ----- | ------- |
| **KernelMode** | **String** points to kernel-mode memory. The function performs a direct string length calculation. See Remarks for more details. |
| **UserMode** | **String** points to user-mode memory. The function raises an exception if **String** doesn't point to user-mode memory; otherwise it performs a safe string length calculation at the specified address. See Remarks for more details. |

## -syntax

```cpp
FORCEINLINE
SIZE_T
WideStringLengthFromMode (
    _In_ PCWSTR String,
    _In_ SIZE_T MaxLength,
    _In_ KPROCESSOR_MODE Mode
    );
```

## -returns

The function returns the length of the string in wide characters, not including the terminating null character.

## -remarks

This function provides safe access to calculate the length of a null-terminated wide character string in memory. The behavior depends on the processor mode specified:

- When **Mode** is **UserMode**, the function ensures that the string address is a valid user-mode address and performs the operation safely for user-mode memory access.
- When **Mode** is **KernelMode**, the function operates directly on kernel-mode addresses.

When the mode is **UserMode**, the function includes validation to prevent kernel crashes when accessing potentially invalid user-mode pointers. When the mode is **KernelMode**, it operates on known-safe kernel addresses for optimal performance.

The function raises a structured exception if the operation fails, such as when the string address is not accessible or is invalid for the specified mode.

This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**WideStringLengthFromUser**](nf-usermode_accessors-widestringlengthfromuser.md)

[**StringLengthFromMode**](nf-usermode_accessors-stringlengthfrommode.md)
