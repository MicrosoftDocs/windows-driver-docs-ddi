---
UID: NF:usermode_accessors.InterlockedOr64ToUser
tech.root: kernel
title: InterlockedOr64ToUser
ms.date: 06/24/2025
targetos: Windows
description: The InterlockedOr64ToUser function performs an atomic OR operation on a 64-bit value in user-mode memory.
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
 - InterlockedOr64ToUser
f1_keywords:
 - InterlockedOr64ToUser
 - usermode_accessors/InterlockedOr64ToUser
dev_langs:
 - c++
helpviewer_keywords:
 - InterlockedOr64ToUser
---

## -description

The **InterlockedOr64ToUser** function performs an atomic OR operation on a 64-bit value in user-mode memory.

## -parameters

### -param Destination

[in, out] A pointer to the user-mode memory location containing the first operand. This value will be replaced with the result of the operation.

### -param Value

[in] The second operand.

## -returns

The function returns the original value of the **Destination** parameter.

## -remarks

This function provides atomic access to a 64-bit value in user-mode memory, performing a bitwise OR operation between the value at **Destination** and **Value**. The interlocked functions provide a simple mechanism for synchronizing access to a variable that is shared by multiple threads.

The function ensures that the destination address is a valid user-mode address before performing the atomic operation. It raises a structured exception if the operation fails, such as when the destination address is not a valid user-mode address or is inaccessible.

This function is atomic with respect to calls to other interlocked functions and generates a full memory barrier to ensure that memory operations are completed in order.

This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**InterlockedOr64ToMode**](nf-usermode_accessors-interlockedor64tomode.md)

[**InterlockedOrToUser**](nf-usermode_accessors-interlockedortouser.md)

[**InterlockedAnd64ToUser**](nf-usermode_accessors-interlockedand64touser.md)
