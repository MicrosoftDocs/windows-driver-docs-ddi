---
UID: NS:ntifs._SET_DAX_ALLOC_ALIGNMENT_HINT_INPUT
title: _SET_DAX_ALLOC_ALIGNMENT_HINT_INPUT (ntifs.h)
description: This structure is for internal use only and should not be called from your code.
old-location: ifsk\set_dax_alloc_alignment_hint_input.htm
tech.root: ifsk
ms.assetid: 62C15E35-D9B6-449D-9AF2-F8A1F75C2BB9
ms.date: 03/29/2018
keywords: ["SET_DAX_ALLOC_ALIGNMENT_HINT_INPUT structure"]
ms.keywords: "PSET_DAX_ALLOC_ALIGNMENT_HINT_INPUT, *PSET_DAX_ALLOC_ALIGNMENT_HINT_INPUT, PSET_DAX_ALLOC_ALIGNMENT_HINT_INPUT structure pointer [Installable File System Drivers], SET_DAX_ALLOC_ALIGNMENT_HINT_INPUT, SET_DAX_ALLOC_ALIGNMENT_HINT_INPUT structure [Installable File System Drivers], _SET_DAX_ALLOC_ALIGNMENT_HINT_INPUT, ifsk.set_dax_alloc_alignment_hint_input, ntifs/PSET_DAX_ALLOC_ALIGNMENT_HINT_INPUT, ntifs/SET_DAX_ALLOC_ALIGNMENT_HINT_INPUT"
f1_keywords:
 - "ntifs/SET_DAX_ALLOC_ALIGNMENT_HINT_INPUT"
 - "SET_DAX_ALLOC_ALIGNMENT_HINT_INPUT"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10, version 1709.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntifs.h
api_name:
- SET_DAX_ALLOC_ALIGNMENT_HINT_INPUT
targetos: Windows
req.typenames: SET_DAX_ALLOC_ALIGNMENT_HINT_INPUT, *PSET_DAX_ALLOC_ALIGNMENT_HINT_INPUT
---


# _SET_DAX_ALLOC_ALIGNMENT_HINT_INPUT structure

## -description

Once this file system control is issued for a file, the following allocations to the file will be examined to see if the given offset is being allocated. If so, the allocation's physical address will be aligned to the given AlignmentValue if enough free space is available at the aligned regions.

To reset the alignment constraint you can issue this FSCTL with AlignmentValue of 1 i.e. AlignmentShift as 0.

## -struct-fields

### -field Flags

The flags used for the file system control. There are two flags that can be used:

* DAX_ALLOC_ALIGNMENT_FLAG_MANDATORY
    * MANDATORY - If allocation satisyfing AlignmentShift (or at least FallbackAlignmentShift if specified) cannot be found, then fail the file system operation (e.g. extending the file).

* DAX_ALLOC_ALIGNMENT_FLAG_FALLBACK_SPECIFIED
    * FALLBACK_SPECIFIED - Indicates that the FallbackAlignmentShift field is present in the input structure and indicates a fallback alignment if the optimal alignment isn't available.

### -field AlignmentShift

The block size used to align the given offset of the file. The file is allocated so that the file's physical address is aligned to this block size.

The actual alignment value is given by:

```cpp
AlignmentValue = (1 << AlignmentShift);
```

### -field FileOffsetToAlign

The file offset that should be aligned to the given AlignmentValue. This should be cluster aligned.

> [!NOTE] 
> MM supports huge page only if the file offset and the physical address are 1gb aligned.
 
### -field FallbackAlignmentShift

If DAX_ALLOC_ALIGNMENT_FLAG_FALLBACK_SPECIFIED is present in Flags, this field specifies a fallback block size to align the given offset of the file whenever allocation satisfying AlignmentShift could not be found. 

## -remarks

## -see-also
