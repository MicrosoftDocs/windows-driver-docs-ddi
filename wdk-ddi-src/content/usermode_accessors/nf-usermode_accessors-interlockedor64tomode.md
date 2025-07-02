---
UID: NF:usermode_accessors.InterlockedOr64ToMode
tech.root: kernel
title: InterlockedOr64ToMode
ms.date: 06/24/2025
targetos: Windows
description: The InterlockedOr64ToMode function performs an atomic OR operation on a 64-bit value in memory, with access dependent on the processor mode.
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
 - InterlockedOr64ToMode
f1_keywords:
 - InterlockedOr64ToMode
 - usermode_accessors/InterlockedOr64ToMode
dev_langs:
 - c++
helpviewer_keywords:
 - InterlockedOr64ToMode
---

## -description

The **InterlockedOr64ToMode** function performs an atomic OR operation on a 64-bit value, based on the specified processor mode.

## -parameters

### -param Destination

[in, out] A pointer to the memory location containing the first operand. This value will be replaced with the result of the operation.

### -param Value

[in] The second operand.

### -param Mode

[in] The processor mode that determines how the memory access is performed. **Mode** can be one of the following values.

| Value | Meaning |
| ----- | ------- |
| **KernelMode** | **Destination** points to kernel-mode memory. The function performs a direct atomic OR operation. See Remarks for more details. |
| **UserMode** | **Destination** points to user-mode memory. The function raises an exception if **Destination** doesn't point to user-mode memory; otherwise it performs an atomic OR operation at the specified address. See Remarks for more details. |

## -returns

The function returns the original value of the **Destination** parameter.

## -remarks

This function provides atomic access to a 64-bit value in memory, performing a bitwise OR operation between the value at **Destination** and **Value**. The behavior depends on the processor mode specified:

- When **Mode** is **UserMode**, the function ensures that the destination address is a valid user-mode address and performs the operation safely for user-mode memory access.
- When **Mode** is **KernelMode**, the function operates directly on kernel-mode addresses.

The interlocked functions provide a simple mechanism for synchronizing access to a variable that is shared by multiple threads. This function is atomic with respect to calls to other interlocked functions and generates a full memory barrier to ensure that memory operations are completed in order.

The function raises a structured exception if the operation fails, such as when the destination address is not accessible or is invalid for the specified mode.

This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**InterlockedOr64ToUser**](nf-usermode_accessors-interlockedor64touser.md)

[**InterlockedOrToMode**](nf-usermode_accessors-interlockedortomode.md)

[**InterlockedAnd64ToMode**](nf-usermode_accessors-interlockedand64tomode.md)
