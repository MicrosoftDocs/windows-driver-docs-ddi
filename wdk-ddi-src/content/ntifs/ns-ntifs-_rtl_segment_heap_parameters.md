---
UID: NS:ntifs._RTL_SEGMENT_HEAP_PARAMETERS
title: _RTL_SEGMENT_HEAP_PARAMETERS (ntifs.h)
description: The RTL_SEGMENT_HEAP_PARAMETERS structure contains the segment heap parameters.
ms.date: 10/19/2018
tech.root: ifsk
keywords: ["RTL_SEGMENT_HEAP_PARAMETERS structure"]
ms.keywords: _RTL_SEGMENT_HEAP_PARAMETERS, RTL_SEGMENT_HEAP_PARAMETERS, *PRTL_SEGMENT_HEAP_PARAMETERS,
req.header: ntifs.h
req.include-header: 
req.target-type: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: RTL_SEGMENT_HEAP_PARAMETERS, *PRTL_SEGMENT_HEAP_PARAMETERS
targetos: Windows
f1_keywords:
 - _RTL_SEGMENT_HEAP_PARAMETERS
 - ntifs/_RTL_SEGMENT_HEAP_PARAMETERS
 - PRTL_SEGMENT_HEAP_PARAMETERS
 - ntifs/PRTL_SEGMENT_HEAP_PARAMETERS
 - RTL_SEGMENT_HEAP_PARAMETERS
 - ntifs/RTL_SEGMENT_HEAP_PARAMETERS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _RTL_SEGMENT_HEAP_PARAMETERS
 - PRTL_SEGMENT_HEAP_PARAMETERS
 - RTL_SEGMENT_HEAP_PARAMETERS
---

# _RTL_SEGMENT_HEAP_PARAMETERS structure


The **RTL_SEGMENT_HEAP_PARAMETERS** structure contains the segment heap parameters.


## -description

## -struct-fields

### -field Version

Contains the size of this structure, in bytes. The value of this member will change as members are added to the structure.

### -field Size

Specifies the total size of the data returned, in bytes. This may include data that follows this structure.

### -field Flags

The flags associated with the segment heap.

### -field MemorySource

 
Specifies the memory source of the Segment heap.

### -field Reserved

Reserved.

## -remarks

## -see-also

