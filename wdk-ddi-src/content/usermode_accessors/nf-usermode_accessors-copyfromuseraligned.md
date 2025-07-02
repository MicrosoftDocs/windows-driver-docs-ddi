---
UID: NF:usermode_accessors.CopyFromUserAligned
tech.root: kernel
title: CopyFromUserAligned
ms.date: 07/02/2025
targetos: Windows
description: The CopyFromUserAligned macro safely copies data from user-mode memory to kernel memory, with alignment checking.
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
 - CopyFromUserAligned
f1_keywords:
 - CopyFromUserAligned
 - usermode_accessors/CopyFromUserAligned
dev_langs:
 - c++
helpviewer_keywords:
 - CopyFromUserAligned
---

## -description

The **CopyFromUserAligned** macro safely copies data from user-mode memory to kernel memory, with alignment checking.

## -parameters

### -param Destination

[out] A pointer to the kernel memory location where the data will be copied.

### -param Source

[in] A pointer to the user-mode memory location from which to copy the data.

### -param Length

[in] The number of bytes to copy.

### -param Alignment

[in] The alignment boundary that the source pointer must satisfy.

## -remarks

This macro provides a safe way to copy data from user-mode memory to kernel memory with alignment verification.

The macro ensures that the source address is a valid user-mode address and meets the alignment requirements before performing the copy operation.

The macro validates that the destination pointer refers to kernel memory and raises a structured exception if the copy operation fails, such as when the source address is not a valid user-mode address, is inaccessible, or doesn't meet the alignment requirements.

This macro will never be optimized away by the compiler, nor will the compiler create additional accesses to this memory location before the macro is called or after the macro returns (unless the source code explicitly performs these accesses). The memory access is performed with [memory_order_relaxed semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum).

This macro works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the macro definition from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**CopyFromUser**](nf-usermode_accessors-copyfromuser.md)

[**CopyFromUserNonTemporal**](nf-usermode_accessors-copyfromusernontemporal.md)

[**CopyFromMode**](nf-usermode_accessors-copyfrommode.md)

[**CopyFromModeAligned**](nf-usermode_accessors-copyfrommodealigned.md)

[**CopyToUser**](nf-usermode_accessors-copytouser.md)
