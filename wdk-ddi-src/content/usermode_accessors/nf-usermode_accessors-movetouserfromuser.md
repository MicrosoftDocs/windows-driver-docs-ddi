---
UID: NF:usermode_accessors.MoveToUserFromUser
tech.root: kernel
title: MoveToUserFromUser
ms.date: 06/24/2025
targetos: Windows
description: The MoveToUserFromUser function safely moves data from user-mode memory to user-mode memory, supporting overlapping memory regions.
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
 - MoveToUserFromUser
f1_keywords:
 - MoveToUserFromUser
 - usermode_accessors/MoveToUserFromUser
dev_langs:
 - c++
helpviewer_keywords:
 - MoveToUserFromUser
---

## -description

The **MoveToUserFromUser** function safely moves data from user-mode memory to user-mode memory, supporting overlapping memory regions.

## -parameters

### -param Destination

[out] A pointer to the user-mode memory location where the data will be moved.

### -param Source

[in] A pointer to the user-mode memory location from which to move the data.

### -param Length

[in] The number of bytes to move.

## -remarks

This function provides a safe way to move data from user-mode memory to user-mode memory with support for overlapping memory regions (memmove semantics). It ensures that both source and destination addresses are valid user-mode addresses before performing the move operation.

Unlike copy operations, this function correctly handles the case where the source and destination memory regions overlap, ensuring data integrity during the operation.

The function validates that both pointers refer to user-mode memory and raises a structured exception if the move operation fails, such as when the source or destination addresses are not valid user-mode addresses or are inaccessible.

This function will never be optimized away by the compiler, nor will the compiler create additional accesses to this memory location before the function is called or after the function returns (unless the source code explicitly performs these accesses). The memory access is performed with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum).

This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**CopyToUserFromUser**](nf-usermode_accessors-copytouserfromuser.md)

[**CopyToUser**](nf-usermode_accessors-copytouser.md)

[**CopyFromUser**](nf-usermode_accessors-copyfromuser.md)
