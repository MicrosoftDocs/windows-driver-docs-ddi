---
UID: NF:usermode_accessors.WriteStructToUser
tech.root: kernel
title: WriteStructToUser
ms.date: 07/02/2025
targetos: Windows
description: The WriteStructToUser macro safely writes a structure to user-mode memory.
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
 - WriteStructToUser
f1_keywords:
 - WriteStructToUser
 - usermode_accessors/WriteStructToUser
dev_langs:
 - c++
helpviewer_keywords:
 - WriteStructToUser
ai-usage: ai-assisted
---

## -description

The **WriteStructToUser** macro safely writes a structure to user-mode memory.

## -parameters

### -param Destination

[out] A pointer to the user-mode memory location where the structure will be written.

### -param Source

[in] A pointer to the structure to write to the destination memory location.

## -remarks

This macro provides a safe way to write a structure to user-mode memory. It ensures the provided address is a user-mode address before writing to it.

The macro validates that **Source** and **Destination** point to compatible types and automatically determines the structure size for the copy operation.

This macro doesn't enforce alignment.

It raises a structured exception if the memory access fails, such as when the destination address isn't a user-mode address or is inaccessible.

This macro will never be optimized away by the compiler, nor will the compiler create additional accesses to this memory location before the macro is called or after the macro returns (unless the source code explicitly performs these accesses). The memory access is performed with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum).

This macro works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the macro declaration from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**ReadStructFromUser**](nf-usermode_accessors-readstructfromuser.md)

[**WriteStructToMode**](nf-usermode_accessors-writestructtomode.md)

[**WriteStructToUserHelper**](nf-usermode_accessors-writestructtouserhelper.md)
