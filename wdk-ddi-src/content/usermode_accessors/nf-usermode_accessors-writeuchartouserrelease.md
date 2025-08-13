---
UID: NF:usermode_accessors.WriteUCharToUserRelease
tech.root: kernel
title: WriteUCharToUserRelease
ms.date: 07/02/2025
targetos: Windows
description: The WriteUCharToUserRelease function safely writes a UCHAR value to user-mode memory with release semantics.
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
 - WriteUCharToUserRelease
f1_keywords:
 - WriteUCharToUserRelease
 - usermode_accessors/WriteUCharToUserRelease
dev_langs:
 - c++
helpviewer_keywords:
 - WriteUCharToUserRelease
ai-usage: ai-assisted
---

## -description

The **WriteUCharToUserRelease** function safely writes a UCHAR value to user-mode memory with [release semantics](/windows-hardware/drivers/kernel/acquire-and-release-semantics).

## -parameters

### -param Destination

[out] A pointer to the user-mode memory location where the UCHAR value will be written.

### -param Value

[in] The UCHAR value to write to the destination memory location.

## -syntax

```cpp
FORCEINLINE
VOID
Writeuchartouserrelease (
    _Out_ volatile UCHAR* Destination,
    _In_ UCHAR Value
    );
```

## -remarks

This function provides a safe way to write a UCHAR value to user-mode memory. It ensures the provided address is a user-mode address before writing to it. The [release semantics](/windows-hardware/drivers/kernel/acquire-and-release-semantics) ensure that preceding memory operations can't be reordered after this write operation.

This function doesn't enforce alignment.

It raises a structured exception if the memory access fails, such as when the destination address isn't a user-mode address or is inaccessible.

This function will never be optimized away by the compiler, nor will the compiler create additional accesses to this memory location before the function is called or after the function returns (unless the source code explicitly performs these accesses). The memory access is performed with [memory_order_release semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum).

This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**WriteUCharToUser**](nf-usermode_accessors-writeuchartouser.md)

[**ReadUCharFromUserAcquire**](nf-usermode_accessors-readucharfromuseracquire.md)
