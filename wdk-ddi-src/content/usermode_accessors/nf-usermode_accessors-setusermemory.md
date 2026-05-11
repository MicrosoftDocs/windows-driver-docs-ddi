---
UID: NF:usermode_accessors.SetUserMemory
tech.root: kernel
title: SetUserMemory
ms.date: 07/02/2025
targetos: Windows
description: The SetUserMemory function fills a user-mode memory region with a specified byte value.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: usermode_accessors.h
req.idl: 
req.include-header: 
req.irql: <= APC_LEVEL
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
 - SetUserMemory
f1_keywords:
 - SetUserMemory
 - usermode_accessors/SetUserMemory
dev_langs:
 - c++
helpviewer_keywords:
 - SetUserMemory
ai-usage: ai-assisted
---

## -description

The **SetUserMemory** function fills a user-mode memory region with a specified byte value.

## -parameters

### -param Destination

[out] A pointer to the starting address of the memory block to fill.

### -param Fill

[in] The byte value used to fill the first **Length** bytes of **Destination**.

### -param Length

[in] The number of bytes to fill with the **Fill** value.

## -remarks

This function provides a safe way to fill a user-mode memory region with a specified byte value. This allows for flexible memory operations when kernel-mode code needs to initialize user-mode memory buffers.

The function has the following properties:

* The function performs a volatile fill using [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum).

* The function isn't recognized as a compiler intrinsic so the compiler will never optimize away the call (either entirely or replace the call with an equivalent sequence of instructions).

* When the call returns, the buffer has been overwritten with the specified **Fill** value. This function's memory accesses to the **Destination** will only be performed within the function (for example, the compiler can't move memory accesses out of this function).

* The function might perform unaligned memory accesses if the platform allows for it.

* The function might access memory locations more than once as part of its fill operation.

The function raises a structured exception if the fill operation fails, such as when the destination address is not a valid user-mode address or is inaccessible.

This function will never be optimized away by the compiler, nor will the compiler create additional accesses to this memory location before the function is called or after the function returns (unless the source code explicitly performs these accesses).

This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**SetModeMemory**](nf-usermode_accessors-setmodememory.md)

[**FillUserMemory**](nf-usermode_accessors-fillusermemory.md)

[**ZeroUserMemory**](nf-usermode_accessors-zerousermemory.md)

[**CopyToUser**](nf-usermode_accessors-copytouser.md)
