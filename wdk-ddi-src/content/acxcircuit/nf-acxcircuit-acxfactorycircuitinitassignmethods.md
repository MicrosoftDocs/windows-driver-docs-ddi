---
UID: NF:acxcircuit.AcxFactoryCircuitInitAssignMethods
tech.root: audio
title: AcxFactoryCircuitInitAssignMethods
ms.date: 08/18/2021
targetos: Windows
description: The AcxCircuitFactoryInitAssignMethods function assigns one or more Methods that will be used for the circuit initialization.
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
 - AcxFactoryCircuitInitAssignMethods
f1_keywords:
 - AcxFactoryCircuitInitAssignMethods
 - acxcircuit/AcxFactoryCircuitInitAssignMethods
dev_langs:
 - c++
---

## -description

The AcxFactoryCircuitInitAssignMethods function assigns one or more Methods that will be used for the circuit initialization.

## -parameters

### -param FactoryInit

TBD - An ACXFACTORYCIRCUIT_INIT structure that is used for circuit factory initialization. This is an opaque structure that is used to store ACX Circuit factory initialization information and associate the factory with a WDF device.
Use the [AcxFactoryCircuitInitAllocate function](nf-acxcircuit-acxfactorycircuitinitallocate.md) to initialize the ACXFACTORYCIRCUIT_INIT structure.

### -param Methods

TBD - An [ACX_METHOD_ITEM structure](/windows-hardware/drivers/ddi/acxrequest/ns-acxrequest-acx_method_item) structure that defines a set of TBD TBD and is used to TBD. 

### -param MethodsCount

TBD - The number of methods that will be added to the circuit. This is a TBD zero / one based count.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
typedef enum {
    KSMETHOD_APXCIRCUITFACTORY_ADD_CIRCUIT        = 1,
    KSMETHOD_APXCIRCUITFACTORY_REMOVE_CIRCUIT     = 2,
} KSMETHOD_APXCIRCUITFACTORY;

static ACX_METHOD_ITEM s_FactoryCircuitMethods[] =
{
    {
        &KSMETHODSETID_ApxCircuitFactory,
        KSMETHOD_APXCIRCUITFACTORY_ADD_CIRCUIT,
        ACX_METHOD_ITEM_FLAG_SEND,
        &C_EvtAddCircuitCallback,
        NULL,                                       // Reserved
        sizeof(APX_CIRCUIT_FACTORY_ADD_CIRCUIT),    // ControlCb
        0,                                          // ValueCb
    },
    /*
    {
        &KSMETHODSETID_ApxCircuitFactory,
        KSMETHOD_APXCIRCUITFACTORY_REMOVE_CIRCUIT,
        ACX_METHOD_ITEM_FLAG_SEND,
        &EvtRemoveCircuitCallback,
        NULL,                                       // Reserved
        sizeof(APX_CIRCUIT_FACTORY_REMOVE_CIRCUIT), // ControlCb
        0,                                          // ValueCb
    },
    */
};
    //
    // Get a FactoryCircuitInit structure.
    //
    factoryInit = AcxFactoryCircuitInitAllocate(Device);

    //
    // Add factory identifiers.
    //
    AcxFactoryCircuitInitSetComponentId(factoryInit, &KSCATEGORY_APXCIRCUITFACTORY);
    AcxFactoryCircuitInitAssignCategories(factoryInit, &KSCATEGORY_APXCIRCUITFACTORY, 1);
    AcxFactoryCircuitInitAssignName(factoryInit, &s_FactoryName);

    //
    // Add properties, events and methods.
    //
    status = AcxFactoryCircuitInitAssignMethods(factoryInit,
                                                s_FactoryCircuitMethods,
                                                s_FactoryCircuitMethodsCount);

```

## -see-also

[acxcircuit.h header](index.md)

