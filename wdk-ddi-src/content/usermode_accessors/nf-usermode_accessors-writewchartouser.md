---
UID: NF:usermode_accessors.WriteWCharToUser
tech.root: kernel
title: WriteWCharToUser
ms.date: 06/24/2025
targetos: Windows
description: The WriteWCharToUser function safely writes a WCHAR value to user-mode memory.
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
 - WriteWCharToUser
f1_keywords:
 - WriteWCharToUser
 - usermode_accessors/WriteWCharToUser
dev_langs:
 - c++
helpviewer_keywords:
 - WriteWCharToUser
---

## -description

The **WriteWCharToUser** function safely writes a WCHAR value to user-mode memory.

## -parameters

### -param Destination

[out] A pointer to the user-mode memory location where the WCHAR value will be written.

### -param Value

[in] The WCHAR value to write to the destination memory location.

## -remarks

This function provides a safe way to write a WCHAR value to user-mode memory. It ensures the provided address is a user-mode address before writing to it.

This function doesn't enforce alignment.

It raises a structured exception if the memory access fails, such as when the destination address isn't a user-mode address or is inaccessible.

This function will never be optimized away by the compiler, nor will the compiler create additional accesses to this memory location before the function is called or after the function returns (unless the source code explicitly performs these accesses). The memory access is performed with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum).

This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**ReadWCharFromUser**](nf-usermode_accessors-readwcharfromuser.md)

[**WriteWCharToUserMode**](nf-usermode_accessors-writewchartomode.md)
