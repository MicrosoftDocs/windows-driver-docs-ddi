---
UID: NF:usermode_accessors.CopyToUserFromUser
tech.root: kernel
title: CopyToUserFromUser
ms.date: 06/24/2025
targetos: Windows
description: The CopyToUserFromUser function safely copies data from user-mode memory to user-mode memory.
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
 - CopyToUserFromUser
f1_keywords:
 - CopyToUserFromUser
 - usermode_accessors/CopyToUserFromUser
dev_langs:
 - c++
helpviewer_keywords:
 - CopyToUserFromUser
---

## -description

The **CopyToUserFromUser** function safely copies data from user-mode memory to user-mode memory.

## -parameters

### -param Destination

[out] A pointer to the user-mode memory location where the data will be copied.

### -param Source

[in] A pointer to the user-mode memory location from which to copy the data.

### -param Length

[in] The number of bytes to copy.

## -remarks

This function provides a safe way to copy data between user-mode memory locations. It ensures that both the source and destination addresses are valid user-mode addresses before performing the copy operation.

The function raises a structured exception if the copy operation fails, such as when either address is not a valid user-mode address or is inaccessible.

This function is useful when kernel-mode code needs to copy data between different user-mode buffers, such as when processing I/O operations that involve multiple user-mode memory regions.

This function will never be optimized away by the compiler, nor will the compiler create additional accesses to this memory location before the function is called or after the function returns (unless the source code explicitly performs these accesses). The memory access is performed with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum).

This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**CopyToUser**](nf-usermode_accessors-copytouser.md)

[**CopyFromUser**](nf-usermode_accessors-copyfromuser.md)

[**MoveToUserFromUser**](nf-usermode_accessors-movetouserfromuser.md)
