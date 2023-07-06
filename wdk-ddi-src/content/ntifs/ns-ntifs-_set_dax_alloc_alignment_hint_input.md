---
UID: NS:ntifs._SET_DAX_ALLOC_ALIGNMENT_HINT_INPUT
title: SET_DAX_ALLOC_ALIGNMENT_HINT_INPUT (ntifs.h)
description: Learn more about the SET_DAX_ALLOC_ALIGNMENT_HINT_INPUT structure.
tech.root: ifsk
ms.date: 07/06/2023
keywords: ["SET_DAX_ALLOC_ALIGNMENT_HINT_INPUT structure"]
ms.keywords: "PSET_DAX_ALLOC_ALIGNMENT_HINT_INPUT, *PSET_DAX_ALLOC_ALIGNMENT_HINT_INPUT, PSET_DAX_ALLOC_ALIGNMENT_HINT_INPUT structure pointer [Installable File System Drivers], SET_DAX_ALLOC_ALIGNMENT_HINT_INPUT, SET_DAX_ALLOC_ALIGNMENT_HINT_INPUT structure [Installable File System Drivers], _SET_DAX_ALLOC_ALIGNMENT_HINT_INPUT, ifsk.set_dax_alloc_alignment_hint_input, ntifs/PSET_DAX_ALLOC_ALIGNMENT_HINT_INPUT, ntifs/SET_DAX_ALLOC_ALIGNMENT_HINT_INPUT"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
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
targetos: Windows
req.typenames: SET_DAX_ALLOC_ALIGNMENT_HINT_INPUT, *PSET_DAX_ALLOC_ALIGNMENT_HINT_INPUT
f1_keywords:
 - _SET_DAX_ALLOC_ALIGNMENT_HINT_INPUT
 - ntifs/_SET_DAX_ALLOC_ALIGNMENT_HINT_INPUT
 - PSET_DAX_ALLOC_ALIGNMENT_HINT_INPUT
 - ntifs/PSET_DAX_ALLOC_ALIGNMENT_HINT_INPUT
 - SET_DAX_ALLOC_ALIGNMENT_HINT_INPUT
 - ntifs/SET_DAX_ALLOC_ALIGNMENT_HINT_INPUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ntifs.h
api_name:
 - _SET_DAX_ALLOC_ALIGNMENT_HINT_INPUT
 - PSET_DAX_ALLOC_ALIGNMENT_HINT_INPUT
 - SET_DAX_ALLOC_ALIGNMENT_HINT_INPUT
---

# SET_DAX_ALLOC_ALIGNMENT_HINT_INPUT structure

## -description

After Windows issues the SET_DAX_ALLOC_ALIGNMENT_HINT_INPUT file system control for a file, it examines allocations to the file.

Once this file system control is issued for a file, the following allocations to the file will be examined to see if the given offset is being allocated. If so, the allocation's physical address will be aligned to the given **AlignmentValue** if enough free space is available at the aligned regions.

## -struct-fields

### -field Flags

The flags used for the file system control. There are two flags that can be used:

| Value | Meaning |
| ----- | ------- |
| DAX_ALLOC_ALIGNMENT_FLAG_MANDATORY | If allocation satisfying **AlignmentShift** (or at least **FallbackAlignmentShift** if specified) can't be found, then fail the file system operation (e.g. extending the file). |
| DAX_ALLOC_ALIGNMENT_FLAG_FALLBACK_SPECIFIED | Indicates that the FallbackAlignmentShift field is present in the input structure and indicates a fallback alignment if the optimal alignment isn't available. |

### -field AlignmentShift

The block size used to align the given offset of the file. The file is allocated so that the file's physical address is aligned to this block size.

The actual alignment value is given by:

```cpp
AlignmentValue = (1 << AlignmentShift);
```

### -field FileOffsetToAlign

The file offset that should be aligned to the given *AlignmentValue*. This should be cluster aligned.

The Memory Manager supports huge page only if the file offset and the physical address are 1gb aligned.

### -field FallbackAlignmentShift

If DAX_ALLOC_ALIGNMENT_FLAG_FALLBACK_SPECIFIED is present in **Flags**, this field specifies a fallback block size to align the given offset of the file whenever allocation satisfying AlignmentShift could not be found.

## -remarks

To reset the alignment constraint you can issue this FSCTL with an *AlignmentValue* of 1; that is, **AlignmentShift** as 0.
