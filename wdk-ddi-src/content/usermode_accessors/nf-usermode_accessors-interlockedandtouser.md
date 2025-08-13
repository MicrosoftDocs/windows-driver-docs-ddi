---
UID: NF:usermode_accessors.InterlockedAndToUser
tech.root: kernel
title: InterlockedAndToUser
ms.date: 07/02/2025
targetos: Windows
description: The InterlockedAndToUser function performs an atomic AND operation on a 32-bit value in user-mode memory.
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
 - InterlockedAndToUser
f1_keywords:
 - InterlockedAndToUser
 - usermode_accessors/InterlockedAndToUser
dev_langs:
 - c++
helpviewer_keywords:
 - InterlockedAndToUser
ai-usage: ai-assisted
---

## -description

The **InterlockedAndToUser** function performs an atomic AND operation on a 32-bit value in user-mode memory.

## -parameters

### -param Destination

[in, out] A pointer to the user-mode memory location containing the first operand. This value will be replaced with the result of the operation. The pointer must be naturally aligned for the data type; that is, the memory location must be 4-byte aligned since **Destination** points to a 4-byte type.

### -param Value

[in] The second operand.

## -syntax

```cpp
FORCEINLINE
LONG
InterlockedAndToUser (
    _Inout_ LONG volatile *Destination,
    _In_ LONG Value
    );
```

## -returns

The function returns the original value of the **Destination** parameter.

## -remarks

The interlocked functions provide a simple mechanism for synchronizing access to a variable that is shared by multiple threads. This function is atomic with respect to calls to other interlocked functions. It generates a full memory barrier to ensure that memory operations are completed in order.

This function provides atomic access to a 32-bit value in user-mode memory, performing a bitwise AND operation between the value at **Destination** and **Value**.

The function raises a structured exception if the operation fails, such as when the destination address is not a valid user-mode address or is inaccessible.

This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**InterlockedAndToMode**](nf-usermode_accessors-interlockedandtomode.md)

[**InterlockedAnd64ToUser**](nf-usermode_accessors-interlockedand64touser.md)

[**InterlockedOrToUser**](nf-usermode_accessors-interlockedortouser.md)
