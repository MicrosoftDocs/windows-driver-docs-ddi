---
UID: NF:usermode_accessors.WriteStructToModeHelper
tech.root: kernel
title: WriteStructToModeHelper
ms.date: 07/02/2025
targetos: Windows
description: The WriteStructToModeHelper function is a helper function that safely writes a structure of a specified size to memory based on the specified processor mode.
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
 - WriteStructToModeHelper
f1_keywords:
 - WriteStructToModeHelper
 - usermode_accessors/WriteStructToModeHelper
dev_langs:
 - c++
helpviewer_keywords:
 - WriteStructToModeHelper
---

## -description

The **WriteStructToModeHelper** function is a helper function that safely writes a structure of a specified size to memory based on the specified processor mode.

## -parameters

### -param Destination

[out] A pointer to the memory location where the data will be written.

### -param Source

[in] A pointer to the data to write to the destination memory location.

### -param Size

[in] The size, in bytes, of the data to write.

### -param Mode

[in] The processor mode that determines how the memory access is performed.

## -remarks

This function is a helper function used internally by the usermode accessor macros. It provides mode-aware writing of structures to memory, with extra safety checks when accessing user-mode memory.

## -see-also

[**WriteStructToMode**](nf-usermode_accessors-writestructtomode.md)

[**WriteStructToModeAligned**](nf-usermode_accessors-writestructtomodealigned.md)
