---
UID: NF:usermode_accessors.InterlockedAndToMode
tech.root: kernel
title: InterlockedAndToMode
ms.date: 07/02/2025
targetos: Windows
description: The InterlockedAndToMode function performs an atomic AND operation on a 32-bit value in memory, with access dependent on the processor mode.
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
 - InterlockedAndToMode
f1_keywords:
 - InterlockedAndToMode
 - usermode_accessors/InterlockedAndToMode
dev_langs:
 - c++
helpviewer_keywords:
 - InterlockedAndToMode
---

## -description

The **InterlockedAndToMode** function performs an atomic AND operation on a 32-bit value, based on the specified processor mode.

## -parameters

### -param Destination

[in, out] A pointer to the memory location containing the first operand. This value will be replaced with the result of the operation. The pointer must be naturally aligned for the data type; that is, the memory location must be 4-byte aligned since **Destination** points to a 4-byte type.

### -param Value

[in] The second operand.

### -param Mode

[in] The processor mode that determines how the memory access is performed. **Mode** can be one of the following values.

| Value | Meaning |
| ----- | ------- |
| **KernelMode** | **Destination** points to kernel-mode memory. The function performs a direct atomic AND operation. See Remarks for more details. |
| **UserMode** | **Destination** points to user-mode memory. The function raises an exception if **Destination** doesn't point to user-mode memory; otherwise it performs an atomic AND operation at the specified address. See Remarks for more details. |

## -returns

The function returns the original value of the **Destination** parameter.

## -remarks

The interlocked functions provide a simple mechanism for synchronizing access to a variable that is shared by multiple threads. This function is atomic with respect to calls to other interlocked functions. It generates a full memory barrier to ensure that memory operations are completed in order.

This function provides atomic access to a 32-bit value in memory, performing a bitwise AND operation between the value at **Destination** and **Value**. The behavior depends on the processor mode specified:

- When **Mode** is **UserMode**, the function ensures that the destination address is a valid user-mode address and performs the operation safely for user-mode memory access.
- When **Mode** is **KernelMode**, the function operates directly on kernel-mode addresses.

The function raises a structured exception if the operation fails, such as when the destination address is not accessible or is invalid for the specified mode.

This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**InterlockedAndToUser**](nf-usermode_accessors-interlockedandtouser.md)

[**InterlockedAnd64ToMode**](nf-usermode_accessors-interlockedand64tomode.md)

[**InterlockedOrToMode**](nf-usermode_accessors-interlockedortomode.md)
