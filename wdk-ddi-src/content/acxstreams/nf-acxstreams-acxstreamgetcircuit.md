---
UID: NF:acxstreams.AcxStreamGetCircuit
tech.root: audio
title: AcxStreamGetCircuit
ms.date: 07/12/2021
targetos: Windows
description: The AcxStreamGetCircuit function returns the ACXCIRCUIT Object associated with the stream.
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
 - AcxStreamGetCircuit
f1_keywords:
 - AcxStreamGetCircuit
 - acxstreams/AcxStreamGetCircuit
dev_langs:
 - c++
---

## -description

The AcxStreamGetCircuit function returns the ACXCIRCUIT Object associated with the stream. For more information about ACX Objects, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -parameters

### -param Stream

An existing ACXSTREAM Object. An ACXSTREAM object represents an audio stream created by a circuit.

## -returns

The handle to the ACXCIRCUIT Object associated with the stream.

## -remarks

### Example

Example usage is shown below.

```cpp
    ACXCIRCUIT circuit = AcxStreamGetCircuit(stream);
```

## -see-also

- [acxstreams.h header](index.md)

READY2GO