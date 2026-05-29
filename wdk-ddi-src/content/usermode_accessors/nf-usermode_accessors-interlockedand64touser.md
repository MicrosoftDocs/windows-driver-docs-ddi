---
UID: NF:usermode_accessors.InterlockedAnd64ToUser
tech.root: kernel
title: InterlockedAnd64ToUser
ms.date: 07/02/2025
targetos: Windows
description: The InterlockedAnd64ToUser function performs an atomic AND operation on a 64-bit value in user-mode memory.
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
 - InterlockedAnd64ToUser
f1_keywords:
 - InterlockedAnd64ToUser
 - usermode_accessors/InterlockedAnd64ToUser
dev_langs:
 - c++
helpviewer_keywords:
 - InterlockedAnd64ToUser
ai-usage: ai-assisted
---

## -description

The **InterlockedAnd64ToUser** function performs an atomic AND operation on a 64-bit value in user-mode memory.

## -parameters

### -param Destination

[in, out] A pointer to the user-mode memory location containing the first operand. This value will be replaced with the result of the operation. The pointer must be naturally aligned for the data type; that is, the memory location must be 8-byte aligned since **Destination** points to an 8-byte type.

### -param Value

[in] The second operand.

## -returns

The function returns the original value of the **Destination** parameter.

## -remarks

The interlocked functions provide a simple mechanism for synchronizing access to a variable that is shared by multiple threads. This function is atomic with respect to calls to other interlocked functions. It generates a full memory barrier to ensure that memory operations are completed in order.

This function provides atomic access to a 64-bit value in user-mode memory, performing a bitwise AND operation between the value at **Destination** and **Value**.

The function raises a structured exception if the operation fails, such as when the destination address is not a valid user-mode address or is inaccessible.

This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**InterlockedAnd64ToMode**](nf-usermode_accessors-interlockedand64tomode.md)

[**InterlockedAndToUser**](nf-usermode_accessors-interlockedandtouser.md)

[**InterlockedOr64ToUser**](nf-usermode_accessors-interlockedor64touser.md)

[**InterlockedCompareExchange64ToUser**](nf-usermode_accessors-interlockedcompareexchange64touser.md)
