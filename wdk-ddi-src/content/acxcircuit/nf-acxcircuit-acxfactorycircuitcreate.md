---
UID: NF:acxcircuit.AcxFactoryCircuitCreate
tech.root: audio
title: AcxFactoryCircuitCreate
ms.date: 07/28/2022
targetos: Windows
description: The AcxFactoryCircuitCreate function is used to create an ACXFACTORYCIRCUIT.
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

The AcxFactoryCircuitCreate function is used to create an ACXFACTORYCIRCUIT.

## -parameters

### -param Device

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that will be associated with the circuit.

### -param Attributes

Additional Attributes defined using a [WDF_OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes) that are used to set the various object’s values: cleanup and destroy callbacks, context type, and to specify its WDF parent object.

### -param Config

The ACXFACTORYCIRCUIT_INIT structure that defines the circuit factory initialization. ACXFACTORYCIRCUIT_INIT is an opaque object used for circuit factory initialization. Use [AcxFactoryCircuitInitAllocate](nf-acxcircuit-acxfactorycircuitinitallocate.md) to initialize the ACXFACTORYCIRCUIT_INIT structure.

### -param Factory

A pointer to a location that receives a handle to the new ACXFACTORYCIRCUIT Object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

The ACXFACTORYCIRCUIT is used by the ACX framework for 'on-demand' ACXCIRCUITs. ACX will ask the ACXFACTORYCIRCUIT to create a new circuit when an endpoint requires one.

The ACXFACTORYCIRCUIT is used in a multi-circuit endpoint. A circuit created by an ACXFACTORYCIRCUIT cannot be the 'core' circuit for the endpoint, i.e., the circuit that gives the endpoint identity.

An ACXFACTORYCIRCUIT has a dedicated WDF queue. For more information about WDF queues, see [Framework Queue Objects](/windows-hardware/drivers/wdf/framework-queue-objects).

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

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxcircuit.h header](index.md)

