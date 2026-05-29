---
UID: NF:usermode_accessors.InterlockedCompareExchange64ToMode
tech.root: kernel
title: InterlockedCompareExchange64ToMode
ms.date: 07/02/2025
targetos: Windows
description: The InterlockedCompareExchange64ToMode function performs an atomic compare-and-exchange operation on a 64-bit value in memory, with access dependent on the processor mode.
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
 - InterlockedCompareExchange64ToMode
f1_keywords:
 - InterlockedCompareExchange64ToMode
 - usermode_accessors/InterlockedCompareExchange64ToMode
dev_langs:
 - c++
helpviewer_keywords:
 - InterlockedCompareExchange64ToMode
ai-usage: ai-assisted
---

## -description

The **InterlockedCompareExchange64ToMode** function performs an atomic compare-and-exchange operation on a 64-bit value, based on the specified processor mode.

## -parameters

### -param Destination

[in, out] A pointer to the memory location containing the destination value. The pointer must be naturally aligned for the data type; that is, the memory location must be 8-byte aligned since **Destination** points to an 8-byte type.

### -param ExChange

[in] The exchange value.

### -param Comperand

[in] The value to compare to **Destination**.

### -param Mode

[in] The processor mode that determines how the memory access is performed. **Mode** can be one of the following values.

| Value | Meaning |
| ----- | ------- |
| **KernelMode** | **Destination** points to kernel-mode memory. The function performs a direct atomic compare-and-exchange operation. See Remarks for more details. |
| **UserMode** | **Destination** points to user-mode memory. The function raises an exception if **Destination** doesn't point to user-mode memory; otherwise it performs an atomic compare-and-exchange operation at the specified address. See Remarks for more details. |

## -returns

The function returns the initial value of the **Destination** parameter.

## -remarks

The interlocked functions provide a simple mechanism for synchronizing access to a variable that is shared by multiple threads. This function is atomic with respect to calls to other interlocked functions. It generates a full memory barrier to ensure that memory operations are completed in order.

This function provides atomic compare-and-exchange access to a 64-bit value in memory. The function compares the **Destination** value with the **Comperand** value. If the **Destination** value is equal to the **Comperand** value, the **ExChange** value is stored in the address specified by **Destination**. Otherwise, no operation is performed. The behavior depends on the processor mode specified:

- When **Mode** is **UserMode**, the function ensures that the destination address is a valid user-mode address and performs the operation safely for user-mode memory access.
- When **Mode** is **KernelMode**, the function operates directly on kernel-mode addresses.

The function raises a structured exception if the operation fails, such as when the destination address is not accessible or is invalid for the specified mode.

This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**InterlockedCompareExchange64ToUser**](nf-usermode_accessors-interlockedcompareexchange64touser.md)

[**InterlockedCompareExchangeToMode**](nf-usermode_accessors-interlockedcompareexchangetomode.md)
