---
UID: NF:usermode_accessors.WriteStructToUserHelper
tech.root: kernel
title: WriteStructToUserHelper
ms.date: 07/02/2025
targetos: Windows
description: The WriteStructToUserHelper function is a helper function that safely writes a structure of a specified size to user-mode memory.
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
 - WriteStructToUserHelper
f1_keywords:
 - WriteStructToUserHelper
 - usermode_accessors/WriteStructToUserHelper
dev_langs:
 - c++
helpviewer_keywords:
 - WriteStructToUserHelper
ai-usage: ai-assisted
---

## -description

The **WriteStructToUserHelper** function is a helper function that safely writes a structure of a specified size to user-mode memory.

## -parameters

### -param Destination

[out] A pointer to the user-mode memory location where the data will be written.

### -param Source

[in] A pointer to the data to write to the destination memory location.

### -param Size

[in] The size, in bytes, of the data to write.

## -syntax

```cpp
FORCEINLINE
NTSTATUS
WriteStructToUserHelper (
    _Out_ PVOID Destination,
    _In_ const PVOID Source,
    _In_ SIZE_T Length
    );
```

## -remarks

This function is a helper function used internally by the user-mode accessor functions. It provides optimized writing of structures to user-mode memory based on the structure size.

## -see-also

[**WriteStructToUser**](nf-usermode_accessors-writestructtouser.md)

[**WriteStructToUserAligned**](nf-usermode_accessors-writestructtouseraligned.md)
