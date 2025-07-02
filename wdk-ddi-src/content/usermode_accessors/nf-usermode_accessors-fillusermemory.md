---
UID: NF:usermode_accessors.FillUserMemory
tech.root: kernel
title: FillUserMemory
ms.date: 06/24/2025
targetos: Windows
description: The FillUserMemory function fills a user-mode memory region with a specified byte value.
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
 - FillUserMemory
f1_keywords:
 - FillUserMemory
 - usermode_accessors/FillUserMemory
dev_langs:
 - c++
helpviewer_keywords:
 - FillUserMemory
---

## -description

The **FillUserMemory** function fills a user-mode memory region with a specified byte value.

## -parameters

### -param Destination

[out] A pointer to the user-mode memory location to fill.

### -param Length

[in] The number of bytes to fill.

### -param Fill

[in] The byte value used to fill the memory region.

## -remarks

This function provides a safe way to fill a user-mode memory region with a specified byte value. It ensures that the destination address is a valid user-mode address before performing the fill operation.

The function validates that the destination pointer refers to user-mode memory and raises a structured exception if the fill operation fails, such as when the destination address is not a valid user-mode address or is inaccessible.

This function will never be optimized away by the compiler, nor will the compiler create additional accesses to this memory location before the function is called or after the function returns (unless the source code explicitly performs these accesses). The memory access is performed with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum).

This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**FillModeMemory**](nf-usermode_accessors-fillmodememory.md)

[**SetUserMemory**](nf-usermode_accessors-setusermemory.md)

[**ZeroUserMemory**](nf-usermode_accessors-zerousermemory.md)

[**CopyToUser**](nf-usermode_accessors-copytouser.md)
