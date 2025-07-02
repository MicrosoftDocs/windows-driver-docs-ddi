---
UID: NF:usermode_accessors.CopyFromUserNonTemporal
tech.root: kernel
title: CopyFromUserNonTemporal
ms.date: 07/02/2025
targetos: Windows
description: The CopyFromUserNonTemporal function safely copies data from user-mode memory to kernel memory using non-temporal instructions.
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
 - CopyFromUserNonTemporal
f1_keywords:
 - CopyFromUserNonTemporal
 - usermode_accessors/CopyFromUserNonTemporal
dev_langs:
 - c++
helpviewer_keywords:
 - CopyFromUserNonTemporal
---

## -description

The **CopyFromUserNonTemporal** function safely copies data from user-mode memory to kernel memory using non-temporal instructions.

## -parameters

### -param Destination

[out] A pointer to the kernel memory location where the data will be copied.

### -param Source

[in] A pointer to the user-mode memory location from which to copy the data.

### -param Length

[in] The number of bytes to copy.

## -remarks

This function provides a safe way to copy data from user-mode memory to kernel memory using non-temporal (streaming) instructions. Non-temporal instructions can improve performance for large data transfers by bypassing the processor cache, reducing cache pollution.

The function validates that the destination pointer refers to kernel memory and raises a structured exception if the copy operation fails, such as when the source address is not a valid user-mode address or is inaccessible.

This function is particularly useful when copying large amounts of data that are unlikely to be accessed again soon, as it avoids evicting other useful data from the cache.

This function will never be optimized away by the compiler, nor will the compiler create additional accesses to this memory location before the function is called or after the function returns (unless the source code explicitly performs these accesses). The memory access is performed with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum).

This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**CopyFromUser**](nf-usermode_accessors-copyfromuser.md)

[**CopyFromModeNonTemporal**](nf-usermode_accessors-copyfrommodenontemporal.md)

[**CopyToUserNonTemporal**](nf-usermode_accessors-copytousernontemporal.md)
