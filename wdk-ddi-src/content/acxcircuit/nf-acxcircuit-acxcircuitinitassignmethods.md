---
UID: NF:acxcircuit.AcxCircuitInitAssignMethods
tech.root: audio
title: AcxCircuitInitAssignMethods
ms.date: 08/17/2021
targetos: Windows
description: The AcxCircuitInitAssignMethods function assigns one or more Methods that will be used for the circuit initialization.
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
 - AcxCircuitInitAssignMethods
f1_keywords:
 - AcxCircuitInitAssignMethods
 - acxcircuit/AcxCircuitInitAssignMethods
dev_langs:
 - c++
---

## -description

The AcxCircuitInitAssignMethods function assigns one or more Methods that will be used for the circuit initialization.

## -parameters

### -param CircuitInit

TBD- The ACXCIRCUIT_INIT structure that defines the circuit initialization. ACXCIRCUIT_INIT is an opaque object used for circuit initialization. Use [AcxCircuitInitAllocate](nf-acxcircuit-acxcircuitinitallocate.md) to initialize the ACXCIRCUIT_INIT structure.

### -param Methods

TBD - An ACX_METHOD_ITEM structure that defines a set of TBD TBD and is used to TBD. 

TODO: DocsTeam add link to this structure in AcxRequest header when available.

### -param MethodsCount

TBD - The number of methods that will be added to the circuit. This is a TBD zero / one based count.


## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp

static ACX_METHOD_ITEM CircuitMethods[] =
{
    {
        &KSMETHODSETID_AcxTestMethod,
        KSMETHOD_ACXCIRCUIT_TEST2_IN2OUT,
        ACX_METHOD_ITEM_FLAG_SEND,
        Amp_EvtTestIn2OutMethodCallback,
        NULL,               // Reserved
        sizeof(ULONG),      // ArgsCb
        sizeof(ULONG),      // ResultCb
    },
};

static ULONG CircuitMethodsCount = SIZEOF_ARRAY(CircuitMethods);


    status = AcxCircuitInitAssignMethods(circuitInit,
                                         CircuitMethods,
                                         CircuitMethodsCount);


```

## -see-also

[acxcircuit.h header](index.md)

