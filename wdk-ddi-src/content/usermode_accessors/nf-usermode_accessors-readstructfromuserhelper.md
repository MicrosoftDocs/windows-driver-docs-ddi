---
UID: NF:usermode_accessors.ReadStructFromUserHelper
tech.root: kernel
title: ReadStructFromUserHelper
ms.date: 06/24/2025
targetos: Windows
description: The ReadStructFromUserHelper function is a helper function that safely reads a structure of a specified size from user-mode memory.
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
 - ReadStructFromUserHelper
f1_keywords:
 - ReadStructFromUserHelper
 - usermode_accessors/ReadStructFromUserHelper
dev_langs:
 - c++
helpviewer_keywords:
 - ReadStructFromUserHelper
---

## -description

The **ReadStructFromUserHelper** function is a helper function that safely reads a structure of a specified size from user-mode memory.

## -parameters

### -param Destination

[out] A pointer to the buffer that receives the data read from user-mode memory.

### -param Source

[in] A pointer to the user-mode memory location from which to read the data.

### -param Size

[in] The size, in bytes, of the data to read.

## -remarks

This function is a helper function used internally by the user-mode accessor macros. It provides optimized reading of structures from user-mode memory based on the structure size.

## -see-also

[**ReadStructFromUser**](nf-usermode_accessors-readstructfromuser.md)

[**ReadStructFromUserAligned**](nf-usermode_accessors-readstructfromuseraligned.md)
