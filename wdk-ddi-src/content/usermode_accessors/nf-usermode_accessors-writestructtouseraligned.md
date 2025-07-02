---
UID: NF:usermode_accessors.WriteStructToUserAligned
tech.root: kernel
title: WriteStructToUserAligned
ms.date: 06/24/2025
targetos: Windows
description: The WriteStructToUserAligned macro safely writes a structure to user-mode memory with alignment validation.
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
 - WriteStructToUserAligned
f1_keywords:
 - WriteStructToUserAligned
 - usermode_accessors/WriteStructToUserAligned
dev_langs:
 - c++
helpviewer_keywords:
 - WriteStructToUserAligned
---

## -description

The **WriteStructToUserAligned** macro safely writes a structure to user-mode memory with alignment validation.

## -parameters

### -param Destination

[out] A pointer to the user-mode memory location where the structure will be written.

### -param Source

[in] A pointer to the structure to write to the destination memory location.

### -param Alignment

[in] The required alignment for the destination address, in bytes.

## -remarks

This macro provides a safe way to write a structure to user-mode memory with alignment enforcement. It ensures the provided address is a user-mode address and meets the specified alignment requirements before writing to it.

The macro validates that **Source** and **Destination** point to compatible types and automatically determines the structure size for the copy operation.

This macro enforces alignment by verifying that the destination address meets the specified alignment requirement. This helps prevent performance penalties and potential hardware faults that can occur when accessing misaligned data structures.

It raises a structured exception if the memory access fails, such as when the destination address isn't a user-mode address, is inaccessible, or doesn't meet the alignment requirements.

This function will never be optimized away by the compiler, nor will the compiler create additional accesses to this memory location before the function is called or after the function returns (unless the source code explicitly performs these accesses). The memory access is performed with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum).

This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**WriteStructToUser**](nf-usermode_accessors-writestructtouser.md)

[**WriteStructToModeAligned**](nf-usermode_accessors-writestructtomodealigned.md)

[**WriteStructToUserHelper**](nf-usermode_accessors-writestructtouserhelper.md)

[**ReadStructFromUserAligned**](nf-usermode_accessors-readstructfromuseraligned.md)
