---
UID: NF:usermode_accessors.ReadStructFromUserAligned
tech.root: kernel
title: ReadStructFromUserAligned
ms.date: 07/02/2025
targetos: Windows
description: The ReadStructFromUserAligned macro safely reads a structure from user-mode memory with alignment validation.
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
 - ReadStructFromUserAligned
f1_keywords:
 - ReadStructFromUserAligned
 - usermode_accessors/ReadStructFromUserAligned
dev_langs:
 - c++
helpviewer_keywords:
 - ReadStructFromUserAligned
---

## -description

The **ReadStructFromUserAligned** macro safely reads a structure from user-mode memory with alignment validation.

## -parameters

### -param Destination

[out] A pointer to the structure that receives the data read from user-mode memory.

### -param Source

[in] A pointer to the user-mode memory location from which to read the structure.

### -param Alignment

[in] The required alignment for the source address, in bytes.

## -remarks

This macro provides a safe way to read a structure from user-mode memory with alignment enforcement. It ensures the provided address is a user-mode address and meets the specified alignment requirements before reading it.

The macro validates that **Source** and **Destination** point to compatible types and automatically determines the structure size for the copy operation.

This macro enforces alignment by verifying that the source address meets the specified alignment requirement. This helps prevent performance penalties and potential hardware faults that can occur when accessing misaligned data structures.

It raises a structured exception if the memory access fails, such as when the source address isn't a user-mode address, is inaccessible, or doesn't meet the alignment requirements.

This macro will never be optimized away by the compiler, nor will the compiler create additional accesses to this memory location before the macro is called or after the macro returns (unless the source code explicitly performs these accesses). The memory access is performed with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum).

This macro works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the macro declaration from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**ReadStructFromUser**](nf-usermode_accessors-readstructfromuser.md)

[**ReadStructFromModeAligned**](nf-usermode_accessors-readstructfrommodealigned.md)

[**ReadStructFromUserHelper**](nf-usermode_accessors-readstructfromuserhelper.md)

[**WriteStructToUserAligned**](nf-usermode_accessors-writestructtouseraligned.md)
