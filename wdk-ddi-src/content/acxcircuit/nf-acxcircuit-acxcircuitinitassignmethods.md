---
UID: NF:acxcircuit.AcxCircuitInitAssignMethods
tech.root: audio
title: AcxCircuitInitAssignMethods
ms.date: 02/01/2022
targetos: Windows
description: The AcxCircuitInitAssignMethods function assigns one or more Methods for the ACXCIRCUIT.
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

The **AcxCircuitInitAssignMethods** function assigns one or more Methods for the ACXCIRCUIT.

## -parameters

### -param CircuitInit

The ACXCIRCUIT_INIT structure that defines the circuit initialization. ACXCIRCUIT_INIT is an opaque object used for circuit initialization. Use [AcxCircuitInitAllocate](nf-acxcircuit-acxcircuitinitallocate.md) to initialize the ACXCIRCUIT_INIT structure.

### -param Methods

An [ACX_METHOD_ITEM](/windows-hardware/drivers/ddi/acxrequest/acxrequest/ns-acxrequest-acx_method_item) structure that defines a set of methods that will be used for circuit initialization.

### -param MethodsCount

The number of methods that will be added to the circuit. This is a one based count.

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

- [acxcircuit.h header](index.md)

READY2GO