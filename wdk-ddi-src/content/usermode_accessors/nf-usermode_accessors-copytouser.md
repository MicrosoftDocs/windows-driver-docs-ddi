---
UID: NF:usermode_accessors.CopyToUser
tech.root: kernel
title: CopyToUser
ms.date: 07/02/2025
targetos: Windows
description: The CopyToUser function safely copies data from kernel memory to user-mode memory.
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
 - CopyToUser
f1_keywords:
 - CopyToUser
 - usermode_accessors/CopyToUser
dev_langs:
 - c++
helpviewer_keywords:
 - CopyToUser
---

## -description

The **CopyToUser** function safely copies data from kernel memory to user-mode memory.

## -parameters

### -param Destination

[out] A pointer to the user-mode memory location where the data will be copied.

### -param Source

[in] A pointer to the kernel memory location from which to copy the data.

### -param Length

[in] The number of bytes to copy.

## -remarks

This function provides a safe way to copy data from kernel memory to user-mode memory. It ensures that the destination address is a valid user-mode address before performing the copy operation.

The function validates that the source pointer refers to kernel memory and raises a structured exception if the copy operation fails, such as when the destination address is not a valid user-mode address or is inaccessible.

This function will never be optimized away by the compiler, nor will the compiler create additional accesses to this memory location before the function is called or after the function returns (unless the source code explicitly performs these accesses). The memory access is performed with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum).

This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**CopyToUserNonTemporal**](nf-usermode_accessors-copytousernontemporal.md)

[**CopyToMode**](nf-usermode_accessors-copytomode.md)

[**CopyFromUser**](nf-usermode_accessors-copyfromuser.md)

[**CopyToUserFromUser**](nf-usermode_accessors-copytouserfromuser.md)
