---
UID: NF:acxcircuit.AcxCircuitAddElements
tech.root: audio
title: AcxCircuitAddElements
ms.date: 08/16/2021
targetos: Windows
description: The AcxCircuitAddElements function adds elements to an existing or new TBD? circuit.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxcircuit.h
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
 - acxcircuit.h
api_name:
 - AcxCircuitAddElements
f1_keywords:
 - AcxCircuitAddElements
 - acxcircuit/AcxCircuitAddElements
dev_langs:
 - c++
---

## -description

The AcxCircuitAddElements function adds elements to an existing or new TBD? circuit.

## -parameters

### -param Circuit

TBD - An existing (TBD?) ACXCIRCUIT circuit object.  (DocsTeam - need link to ACX Object Summary topic).
 
### -param Elements

TBD - An ACXELEMENT circuit object (TBD - array?).  (DocsTeam - need link to ACX Object Summary topic).
 
`_In_reads_(ElementsCount) ACXELEMENT*   Elements,`

### -param ElementsCount

TBD - The number of elements that will be added to the circuit. This is a TBD zero / one based count.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
    ACX_ELEMENT_CONFIG_INIT(&elementCfg);
    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&attributes, CODEC_ELEMENT_CONTEXT);
    attributes.ParentObject = circuit;
    
    status = AcxElementCreate(circuit, &attributes, &elementCfg, &elements[1]);

    elementCtx = GetCodecElementContext(elements[1]);

    //
    // Add the circuit elements
    //
    status = AcxCircuitAddElements(circuit, elements, SIZEOF_ARRAY(elements));
```

## -see-also

[acxcircuit.h header](index.md)

