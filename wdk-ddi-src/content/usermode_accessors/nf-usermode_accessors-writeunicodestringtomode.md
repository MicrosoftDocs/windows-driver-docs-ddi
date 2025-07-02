---
UID: NF:usermode_accessors.WriteUnicodeStringToMode
tech.root: kernel
title: WriteUnicodeStringToMode
ms.date: 06/24/2025
targetos: Windows
description: The WriteUnicodeStringToMode function safely writes a UNICODE_STRING structure to memory based on the specified processor mode.
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
 - WriteUnicodeStringToMode
f1_keywords:
 - WriteUnicodeStringToMode
 - usermode_accessors/WriteUnicodeStringToMode
dev_langs:
 - c++
helpviewer_keywords:
 - WriteUnicodeStringToMode
---

## -description

The **WriteUnicodeStringToMode** function safely writes a [UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure to memory based on the specified processor mode.

## -parameters

### -param Destination

[out] A pointer to the memory location where the [UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure will be written.

### -param Value

[in] The [UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure to write to the destination memory location.

### -param Mode

[in] The processor mode that determines how the memory access is performed. **Mode** can be one of the following values.

| Value | Meaning |
| ----- | ------- |
| **KernelMode** | **Destination** points to kernel-mode memory. The function performs a write to the specified address with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum). See Remarks for more details. |
| **UserMode** | **Destination** points to user-mode memory. The function raises an exception if **Destination** doesn't point to user-mode memory; otherwise it performs a write to the specified address with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum). See Remarks for more details. |

## -remarks

This function provides a safe way to write a [UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure to memory, with extra safety checks when accessing user-mode memory. It ensures that the provided address is valid and accessible based on the specified processor mode.

This function doesn't enforce alignment.

It raises a structured exception if the memory access fails, such as when the destination address is inaccessible or is invalid for the specified mode.

This function will never be optimized away by the compiler, nor will the compiler create additional accesses to this memory location before the function is called or after the function returns (unless the source code explicitly performs these accesses). The memory access is performed with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum).

This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**WriteUnicodeStringToUser**](nf-usermode_accessors-writeunicodestringtouser.md)

[**ReadUnicodeStringFromMode**](nf-usermode_accessors-readunicodestringfrommode.md)
