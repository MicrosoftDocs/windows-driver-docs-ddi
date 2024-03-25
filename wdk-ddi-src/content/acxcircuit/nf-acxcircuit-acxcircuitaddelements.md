---
UID: NF:acxcircuit.AcxCircuitAddElements
tech.root: audio
title: AcxCircuitAddElements
ms.date: 12/14/2022
targetos: Windows
description: The AcxCircuitAddElements function adds elements to an ACXCIRCUIT.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxcircuit.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
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

The **AcxCircuitAddElements** function adds elements to an ACXCIRCUIT.

## -parameters

### -param Circuit

An existing ACXCIRCUIT object.  For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Elements

One or more ACXELEMENT objects that will be added to the circuit.  

### -param ElementsCount

The number of elements that will be added to the circuit. This is a one based count.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

The driver can only add elements to a circuit before the circuit is added to the device.
The driver cannot change the circuit's elements at run time.

### Example

Example usage is shown below.

```cpp

    //
    // Add a second element.
    //
    ACX_ELEMENT_CONFIG_INIT(&elementCfg);
    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&attributes, CODEC_ELEMENT_CONTEXT);
    attributes.ParentObject = circuit;
    
    status = AcxElementCreate(circuit, &attributes, &elementCfg, &elements[1]);

    //
    // Add the elements to the circuit.
    //
    status = AcxCircuitAddElements(circuit, elements, SIZEOF_ARRAY(elements));
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxcircuit.h header](index.md)
