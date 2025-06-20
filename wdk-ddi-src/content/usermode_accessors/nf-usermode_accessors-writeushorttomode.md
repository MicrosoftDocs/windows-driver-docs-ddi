---
UID: NF:usermode_accessors.WriteUShortToMode
tech.root: kernel
title: WriteUShortToMode
ms.date: 06/19/2025
targetos: Windows
description: The WriteUShortToMode function safely writes a USHORT value to memory based on the specified processor mode.
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
 - WriteUShortToMode
f1_keywords:
 - WriteUShortToMode
 - usermode_accessors/WriteUShortToMode
dev_langs:
 - c++
helpviewer_keywords:
 - WriteUShortToMode
---

## -description

The **WriteUShortToMode** function safely writes a USHORT value to memory based on the specified processor mode.

## -parameters

### -param Destination

[out] A pointer to the memory location where the USHORT value will be written.

### -param Value

[in] The USHORT value to write to the destination memory location.

### -param Mode

[in] The processor mode that determines how the memory access is performed. **Mode** can be one of the following values.

| Value | Meaning |
| ----- | ------- |
| **KernelMode** | **Destination** points to kernel-mode memory. The function performs a direct write to the specified address. |
| **UserMode** | **Destination** points to user-mode memory. The function performs a safe write with appropriate checks to ensure the memory is accessible. |

## -remarks

This function provides a safe way to write a USHORT value to memory, with extra safety checks when accessing user-mode memory. It ensures that the provided address is valid and accessible based on the specified processor mode.

This function doesn't enforce alignment.

It raises a structured exception if the memory access fails, such as when the destination address is inaccessible or is invalid for the specified mode.

This function will never be optimized away by the compiler, nor will the compiler create additional accesses to this memory location before the function is called or after the function returns (unless the source code explicitly performs these accesses).

This function works on all versions of Windows, not just the latest. You need to consume the latest WDK to get the function declaration from the *usermode_accessors.h* header. You also need the library (*umaccess.lib*) from the latest WDK. However, the resulting driver will run fine on older versions of Windows.

## -see-also

[**WriteUShortToUser**](nf-usermode_accessors-writeushorttouser.md)

[**ReadUShortFromMode**](nf-usermode_accessors-readushortfrommode.md)
