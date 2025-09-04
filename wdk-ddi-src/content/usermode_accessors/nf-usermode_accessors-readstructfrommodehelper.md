---
UID: NF:usermode_accessors.ReadStructFromModeHelper
tech.root: kernel
title: ReadStructFromModeHelper
ms.date: 07/02/2025
targetos: Windows
description: The ReadStructFromModeHelper function is a helper function that safely reads a structure of a specified size from memory based on the specified processor mode.
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
 - ReadStructFromModeHelper
f1_keywords:
 - ReadStructFromModeHelper
 - usermode_accessors/ReadStructFromModeHelper
dev_langs:
 - c++
helpviewer_keywords:
 - ReadStructFromModeHelper
ai-usage: ai-assisted
---

## -description

The **ReadStructFromModeHelper** function is a helper function that safely reads a structure of a specified size from memory based on the specified processor mode.

## -parameters

### -param Destination

[out] A pointer to the buffer that receives the data read from memory.

### -param Source

[in] A pointer to the memory location from which to read the data.

### -param Size

[in] The size, in bytes, of the data to read.

### -param Mode

[in] The processor mode that determines how the memory access is performed.

## -remarks

This function is a helper function used internally by the user-mode accessor functions. It provides mode-aware reading of structures from memory, with extra safety checks when accessing user-mode memory.

## -see-also

[**ReadStructFromMode**](nf-usermode_accessors-readstructfrommode.md)

[**ReadStructFromModeAligned**](nf-usermode_accessors-readstructfrommodealigned.md)
