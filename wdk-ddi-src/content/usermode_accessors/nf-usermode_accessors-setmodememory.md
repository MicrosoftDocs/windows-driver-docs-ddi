---
UID: NF:usermode_accessors.SetModeMemory
tech.root: kernel
title: SetModeMemory
ms.date: 07/02/2025
targetos: Windows
description: The SetModeMemory function fills a memory region with a specified byte value, based on the specified processor mode.
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
 - SetModeMemory
f1_keywords:
 - SetModeMemory
 - usermode_accessors/SetModeMemory
dev_langs:
 - c++
helpviewer_keywords:
 - SetModeMemory
ai-usage: ai-assisted
---

## -description

The **SetModeMemory** function fills a memory region with a specified byte value, based on the specified processor mode.

## -parameters

### -param Destination

[out] A pointer to starting address of the memory block to fill.

### -param Fill

[in] The byte value used to fill the first **Length** bytes of **Destination**.

### -param Length

[in] The number of bytes to fill with the **Fill** value.

### -param Mode

[in] The processor mode that determines how the memory access is performed. **Mode** can be one of the following values.

| Value | Meaning |
| ----- | ------- |
| **KernelMode** | **Destination** points to kernel-mode memory. The function performs a direct memory fill operation with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum). See Remarks for more details. |
| **UserMode** | **Destination** points to user-mode memory. The function raises an exception if **Destination** doesn't point to user-mode memory; otherwise it performs a fill operation at the specified address with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum). See Remarks for more details. |

## -remarks

This function provides a safe way to fill a memory region with a specified byte value, with the fill mechanism determined by the specified processor mode.

The function has the following properties:

* When **Mode** is **KernelMode**, the function performs a direct memory fill without additional safety checks.

* When **Mode** is **UserMode**, the function validates the pointer is a user-mode address and then performs the fill. The memory access is performed with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum).

* This function isn't recognized as a compiler instrinsic so the compiler will never optimize away the call (either entirely or replace the call with an equivalent sequence of instructions).

* When the call returns, the first **Length** bytes of the buffer have been overwritten with the specified **Fill** value. This function's memory accesses to the **Destination** will only be performed within the function (for example, the compiler can't move memory accesses out of this function).

* The function might perform unaligned memory accesses if the platform allows for it.

* The function might access memory locations more than once as part of its fill operation.

The function raises a structured exception if the fill operation fails, such as when the destination address is not valid for the specified mode or is inaccessible.

This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**SetUserMemory**](nf-usermode_accessors-setusermemory.md)

[**FillModeMemory**](nf-usermode_accessors-fillmodememory.md)

[**ZeroModeMemory**](nf-usermode_accessors-zeromodememory.md)

[**CopyToMode**](nf-usermode_accessors-copytomode.md)
