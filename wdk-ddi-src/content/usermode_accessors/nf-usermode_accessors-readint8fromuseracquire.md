---
UID: NF:usermode_accessors.ReadInt8FromUserAcquire
tech.root: kernel
title: ReadInt8FromUserAcquire
ms.date: 07/02/2025
targetos: Windows
description: The ReadInt8FromUserAcquire function safely reads an INT8 value from user-mode memory with acquire semantics.
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
 - ReadInt8FromUserAcquire
f1_keywords:
 - ReadInt8FromUserAcquire
 - usermode_accessors/ReadInt8FromUserAcquire
dev_langs:
 - c++
helpviewer_keywords:
 - ReadInt8FromUserAcquire
ai-usage: ai-assisted
---

## -description

The **ReadInt8FromUserAcquire** function safely reads an INT8 value from user-mode memory with [acquire semantics](/windows-hardware/drivers/kernel/acquire-and-release-semantics).

## -parameters

### -param Source

[in] A pointer to the user-mode memory location from which to read the INT8 value.

## -returns

**ReadInt8FromUserAcquire** returns the INT8 value read from the specified user-mode memory address.

## -remarks

This function provides a safe way to read an INT8 value from user-mode memory. It ensures the provided address is a user-mode address before reading it. The [acquire semantics](/windows-hardware/drivers/kernel/acquire-and-release-semantics) ensure that subsequent memory operations can't be reordered before this read operation.

This function doesn't enforce alignment.

It raises a structured exception if the memory access fails, such as when the source address isn't a user-mode address or is inaccessible.

This function will never be optimized away by the compiler, nor will the compiler create additional accesses to this memory location before the function is called or after the function returns (unless the source code explicitly performs these accesses). The memory access is performed with [memory_order_acquire semantics](/cpp/standard-library/atomic-enums?view=msvc-170#memory_order_enum).

This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**ReadInt8FromUser**](nf-usermode_accessors-readint8fromuser.md)

[**WriteInt8ToUserRelease**](nf-usermode_accessors-writeint8touserrelease.md)
