---
UID: NF:acxstreams.AcxStreamGetElementById
tech.root: audio
title: AcxStreamGetElementById
ms.date: 02/02/2022
targetos: Windows
description: The AcxStreamGetElementById function returns ACXELEMENT Object for the requested element ID.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxstreams.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
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
 - acxstreams.h
api_name:
 - AcxStreamGetElementById
f1_keywords:
 - AcxStreamGetElementById
 - acxstreams/AcxStreamGetElementById
dev_langs:
 - c++
---

## -description

The AcxStreamGetElementById function returns ACXELEMENT Object for the requested element ID. For more information about ACX Objects, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -parameters

### -param Stream

A pointer to an existing ACXSTREAM Object. An ACXSTREAM object represents an audio stream created by a circuit. The stream is composed of a list of elements created based on the parent circuit’s elements. 

### -param ElementId

The Id of the requested element. 

## -returns

A pointer to a location that receives a handle to the new ACXELEMENT Object.

## -remarks

### Example

Example usage is shown below.

```cpp
    ULONGLONG               index       = GetMessageContext(Event); // Context is an index.
    ACXELEMENT              element     = nullptr;
    //
    // Get the ACX element.
    //
    element = AcxStreamGetElementById(Stream, (ULONG)index);
```


## -see-also

- [acxstreams.h header](index.md)

TBD - Please review this topic