---
UID: NF:acxstreams.AcxStreamAddElements
tech.root: audio
title: AcxStreamAddElements
ms.date: 02/02/2022
targetos: Windows
description: AcxStreamAddElements is used to add stream elements to an AcxStream.
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
 - AcxStreamAddElements
f1_keywords:
 - AcxStreamAddElements
 - acxstreams/AcxStreamAddElements
dev_langs:
 - c++
---

## -description

**AcxStreamAddElements** is used to add stream elements to an AcxStream.

## -parameters

### -param Stream

An existing *ACXSTREAM* Object. An ACXSTREAM object represents an audio stream created by a circuit. The stream can include zero or more elements. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Elements

A pointer to an array of one or more existing *ACXELEMENT* Objects.

### -param ElementsCount

The count of elements to be added. This is a 1 based count.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp

    ACX_ELEMENT_CONFIG_INIT(&elementCfg);
    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&attributes, ELEMENT_CONTEXT);
 
    attributes.ParentObject = stream;
    status = AcxElementCreate(stream, &attributes, &elementCfg, &elements[0]);
    elementCtx = GetElementContext(elements[0]);
 
    ACX_ELEMENT_CONFIG_INIT(&elementCfg);
    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&attributes, ELEMENT_CONTEXT);
 
    attributes.ParentObject = stream;
    status = AcxElementCreate(stream, &attributes, &elementCfg, &elements[1]);
    elementCtx = GetElementContext(elements[1]);
    //
    // Add stream elements
    //
    status = AcxStreamAddElements(stream, elements, SIZEOF_ARRAY(elements));
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxstreams.h header](index.md)
