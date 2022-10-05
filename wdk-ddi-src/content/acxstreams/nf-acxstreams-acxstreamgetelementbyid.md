---
UID: NF:acxstreams.AcxStreamGetElementById
tech.root: audio
title: AcxStreamGetElementById
ms.date: 07/28/2022
targetos: Windows
description: The AcxStreamGetElementById function returns the ACXELEMENT Object handle for the requested element ID.
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

The **AcxStreamGetElementById** function returns the ACXELEMENT Object handle for the requested element ID. For more information about ACX Objects, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -parameters

### -param Stream

An existing ACXSTREAM Object. An ACXSTREAM object represents an audio stream created by a circuit.

### -param ElementId

The Id of the requested element. 

## -returns

The ACXELEMENT Object handle of the requested element, or NULL if the ACXSTREAM doesn't have an ACXELEMENT with the given Id.

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


### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxstreams.h header](index.md)
