---
UID: NF:usermode_accessors.InterlockedCompareExchangeToUser
tech.root: kernel
title: InterlockedCompareExchangeToUser
ms.date: 07/02/2025
targetos: Windows
description: The InterlockedCompareExchangeToUser function performs an atomic compare-and-exchange operation on a 32-bit value in user-mode memory.
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
 - InterlockedCompareExchangeToUser
f1_keywords:
 - InterlockedCompareExchangeToUser
 - usermode_accessors/InterlockedCompareExchangeToUser
dev_langs:
 - c++
helpviewer_keywords:
 - InterlockedCompareExchangeToUser
ai-usage: ai-assisted
---

## -description

The **InterlockedCompareExchangeToUser** function performs an atomic compare-and-exchange operation on a 32-bit value in user-mode memory.

## -parameters

### -param Destination

[in, out] A pointer to the user-mode memory location containing the destination value. The pointer must be naturally aligned for the data type; that is, the memory location must be 4-byte aligned since **Destination** points to a 4-byte type.

### -param ExChange

[in] The exchange value.

### -param Comperand

[in] The value to compare to **Destination**.

## -returns

The function returns the initial value of the **Destination** parameter.

## -remarks

The interlocked functions provide a simple mechanism for synchronizing access to a variable that is shared by multiple threads. This function is atomic with respect to calls to other interlocked functions. It generates a full memory barrier to ensure that memory operations are completed in order.

This function provides atomic compare-and-exchange access to a 32-bit value in user-mode memory. The function compares the **Destination** value with the **Comperand** value. If the **Destination** value is equal to the **Comperand** value, the **ExChange** value is stored in the address specified by **Destination**. Otherwise, no operation is performed.

The function raises a structured exception if the operation fails, such as when the destination address is not a valid user-mode address or is inaccessible.

This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**InterlockedCompareExchangeToMode**](nf-usermode_accessors-interlockedcompareexchangetomode.md)

[**InterlockedCompareExchange64ToUser**](nf-usermode_accessors-interlockedcompareexchange64touser.md)
