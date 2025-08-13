---
UID: NF:usermode_accessors.ReadUInt16FromUser
tech.root: kernel
title: ReadUInt16FromUser
ms.date: 07/02/2025
targetos: Windows
description: The ReadUInt16FromUser function safely reads a UINT16 value from user-mode memory.
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
 - ReadUInt16FromUser
f1_keywords:
 - ReadUInt16FromUser
 - usermode_accessors/ReadUInt16FromUser
dev_langs:
 - c++
helpviewer_keywords:
 - ReadUInt16FromUser
ai-usage: ai-assisted
---

## -description

The **ReadUInt16FromUser** function safely reads a UINT16 value from user-mode memory.

## -parameters

### -param Source

[in] A pointer to the user-mode memory location from which to read the UINT16 value.

## -syntax

```cpp
FORCEINLINE
UINT16
ReadUInt16FromUser (
    _In_ const volatile UINT16* Source
    );
```

## -returns

**ReadUInt16FromUser** returns the UINT16 value read from the specified user-mode memory address.

## -remarks

This function provides a safe way to read a UINT16 value from user-mode memory. It ensures the provided address is a user-mode address before reading it.

This function doesn't enforce alignment.

It raises a structured exception if the memory access fails, such as when the source address isn't a user-mode address or is inaccessible.

This function will never be optimized away by the compiler, nor will the compiler create additional accesses to this memory location before the function is called or after the function returns (unless the source code explicitly performs these accesses). The memory access is performed with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum).

This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**ReadUInt16FromMode**](nf-usermode_accessors-readuint16frommode.md)

[**WriteUInt16ToUser**](nf-usermode_accessors-writeuint16touser.md)
