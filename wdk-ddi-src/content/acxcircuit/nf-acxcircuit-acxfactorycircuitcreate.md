---
UID: NF:acxcircuit.AcxFactoryCircuitCreate
tech.root: audio
title: AcxFactoryCircuitCreate
ms.date: 08/12/2021
targetos: Windows
description: The AcxFactoryCircuitCreate function is used to create a circuit using an AcxFactory. This function is located in the acxcircuit header.
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
 - AcxFactoryCircuitCreate
f1_keywords:
 - AcxFactoryCircuitCreate
 - acxcircuit/AcxFactoryCircuitCreate
dev_langs:
 - c++
---

## -description

The AcxFactoryCircuitCreate function is used to create a circuit using an AcxFactory.

## -parameters

### -param Device

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that TBD has/is will be associated with the circuit and will be the parent under these conditions - TBD TBD.

### -param Attributes

Additional Attributes defined using a [WDF_OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes) structure that are used to set various values and to associate the AcxFactory with the parent WDF device object (TBD???).

TBD - What would be useful set for the driver?

### -param Config

TBD- The ACXFACTORYCIRCUIT_INIT structure that defines the circuit factory initialization. ACXFACTORYCIRCUIT_INIT is an opaque object used for circuit factory initialization. Use [AcxFactoryCircuitInitAllocate](nf-acxcircuit-acxfactorycircuitinitallocate.md) to initialize the ACXFACTORYCIRCUIT_INIT structure.

### -param Factory

A pointer to a location that receives a handle to the new ACXFACTORYCIRCUIT Object. (DocsTeam - need link to ACX Object Summary topic).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).


## -remarks

An AcxFactoryCircuits represents a partial audio path to a user perceived audio device (speakers, mic, etc.). 
An AcxFactoryCircuits aggregates zero or ‘n’ AcxElements-like objects. By default, AcxElements are ‘connected’ in the same order of assembly. 

An AcxCircuit has a dedicated WDF queue. For more information about WDF queues, see [Framework Queue Objects](/windows-hardware/drivers/wdf/framework-queue-objects)


### Example

Example usage is shown below.

```cpp
    NTSTATUS                                        status;
    WDF_OBJECT_ATTRIBUTES                           attributes;
    ACXFACTORYCIRCUIT                               factory;
    PACXFACTORYCIRCUIT_INIT                         factoryInit = NULL;
    SDCAXU_FACTORYCIRCUIT_CONTEXT *                 factoryCtx;
    ACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS         operationCallbacks;

    //
    // Get a FactoryCircuitInit structure.
    //
    factoryInit = AcxFactoryCircuitInitAllocate(Device);

    //
    // Add factory identifiers.
    //
    AcxFactoryCircuitInitSetComponentId(factoryInit, &SDCAXU_FACTORY_GUID);
    AcxFactoryCircuitInitAssignCategories(factoryInit, &SDCAXU_FACTORY_CATEGORY, 1);
    AcxFactoryCircuitInitAssignName(factoryInit, &s_FactoryName);

    //
    // Assign the circuit's operation-callbacks.
    //
    ACX_FACTORY_CIRCUIT_OPERATION_CALLBACKS_INIT(&operationCallbacks);
    operationCallbacks.EvtAcxFactoryCircuitCreateCircuitDevice = SdcaXu_EvtAcxFactoryCircuitCreateCircuitDevice;
    operationCallbacks.EvtAcxFactoryCircuitCreateCircuit = SdcaXu_EvtAcxFactoryCircuitCreateCircuit;
    AcxFactoryCircuitInitSetOperationCallbacks(factoryInit, &operationCallbacks);

    //
    // Create the factory circuit.
    //
    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&attributes, SDCAXU_FACTORYCIRCUIT_CONTEXT);
    attributes.ParentObject = Device;
    status = AcxFactoryCircuitCreate(Device, &attributes, &factoryInit, &factory);


```

## -see-also

[acxcircuit.h header](index.md)

