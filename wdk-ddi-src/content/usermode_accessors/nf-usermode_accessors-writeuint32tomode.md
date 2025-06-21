---
UID: NF:usermode_accessors.WriteUInt32ToMode
tech.root: kernel
title: WriteUInt32ToMode
ms.date: 06/20/2025
targetos: Windows
description: The WriteUInt32ToMode function safely writes a UINT32 value to memory, checking that the address is appropriate for the current processor mode.
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
 - WriteUInt32ToMode
f1_keywords:
 - WriteUInt32ToMode
 - usermode_accessors/WriteUInt32ToMode
dev_langs:
 - c++
helpviewer_keywords:
 - WriteUInt32ToMode
---

## -description

The **WriteUInt32ToMode** function safely writes a UINT32 value to memory, checking that the address is appropriate for the current processor mode.

## -parameters

### -param Destination

[out] A pointer to the memory location where the UINT32 value will be written.

### -param Value

[in] The UINT32 value to write to the specified memory address.

### -param Mode

[in] A value of type **KPROCESSOR_MODE** indicating the processor mode to check against. This can be **UserMode** or **KernelMode**.

## -remarks

This function provides a safe way to write a UINT32 value to memory based on the current processor mode. If **Mode** is **UserMode**, it ensures the provided address is a user-mode address before writing to it. If **Mode** is **KernelMode**, it treats the address as a kernel-mode address.

This function doesn't enforce alignment.

It raises a structured exception if the memory access fails, such as when accessing an inappropriate address for the specified mode or when the address is inaccessible.

This function will never be optimized away by the compiler, nor will the compiler create additional accesses to this memory location before the function is called or after the function returns (unless the source code explicitly performs these accesses). The memory access is performed with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum).

This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**WriteUInt32ToUser**](nf-usermode_accessors-writeuint32touser.md)

[**ReadUInt32FromMode**](nf-usermode_accessors-readuint32frommode.md)
