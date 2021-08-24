---
UID: NC:acxcircuit.EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUIT
tech.root: audio
title: EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUIT
ms.date: 08/24/2021
targetos: Windows
description: TBD - The EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUIT callback is used by the driver to allow it to add additional functionality when a circuit is created, using the TBD function is called,  TBD TBD. 
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
 - LibDef
api_location:
 - acxcircuit.h
api_name:
 - EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUIT
f1_keywords:
 - EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUIT
 - acxcircuit/EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUIT
dev_langs:
 - c++
---

## -description

TBD - The EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUIT callback is used by the driver to allow it to add additional functionality when a circuit is created, using the TBD function is called,  TBD TBD. 

## -parameters

### -param Parent

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that TBD has/is will be the parent under these conditions - TBD TBD 

### -param Device

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that TBD has/is will be the - TBD TBD 

### -param Factory

TBD - The existing circuit factory ACXFACTORYCIRCUIT Object. (DocsTeam - need link to ACX Object Summary topic).

### -param Config

An [ACX_FACTORY_CIRCUIT_ADD_CIRCUIT](ns-acxcircuit-acx_factory_circuit_add_circuit.md) config structure is defines how to add circuits for an ACX circuit factory.

### -param CircuitInit

TBD- The ACXCIRCUIT_INIT structure that defines the circuit initialization. ACXCIRCUIT_INIT is an opaque object used for circuit initialization. Use [AcxCircuitInitAllocate](nf-acxcircuit-acxcircuitinitallocate.md) to initialize the ACXCIRCUIT_INIT structure.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

An AcxFactoryCircuits represents a partial audio path to a user perceived audio device (speakers, mic, etc.). 
An AcxFactoryCircuits aggregates zero or ‘n’ AcxElements-like objects. By default, AcxElements are ‘connected’ in the same order of assembly. 

An AcxCircuit has a dedicated WDF queue. For more information about WDF queues, see [Framework Queue Objects](/windows-hardware/drivers/wdf/framework-queue-objects)

### Example

Example usage is shown below.

TBD - Should we replace msft with contoso?

```cpp
EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUIT Dsp_EvtAcxFactoryCircuitCreateCircuit;

NTSTATUS
Dsp_EvtAcxFactoryCircuitCreateCircuit(
    _In_ WDFDEVICE                          Parent,
    _In_ WDFDEVICE                          Device,
    _In_ ACXFACTORYCIRCUIT                  Factory,
    _In_ PACX_FACTORY_CIRCUIT_ADD_CIRCUIT   CircuitConfig,
    _In_ PACXCIRCUIT_INIT                   CircuitInit
)
{
    ACXOBJECTBAG circuitProperties;

    DECLARE_CONST_ACXOBJECTBAG_DRIVER_PROPERTY_NAME(msft, CircuitId);

    PAGED_CODE();

    NTSTATUS status = STATUS_SUCCESS;

    // Create object bag from the CompositeProperties
    ACX_OBJECTBAG_CONFIG propConfig;
    ACX_OBJECTBAG_CONFIG_INIT(&propConfig);
    propConfig.Handle = CircuitConfig->CircuitProperties;
    propConfig.Flags |= AcxObjectBagConfigOpenWithHandle;

    WDF_OBJECT_ATTRIBUTES attributes;
    WDF_OBJECT_ATTRIBUTES_INIT(&attributes);

    RETURN_NTSTATUS_IF_FAILED(AcxObjectBagOpen(&attributes, &propConfig, &circuitProperties));

    auto cleanupPropConfig = scope_exit([=]() {
        WdfObjectDelete(circuitProperties);
        }
    );

    // Retrieve the intended Circuit ID from the object bag
    GUID circuitId;
    RETURN_NTSTATUS_IF_FAILED(Dsp_DetermineCircuitGuidFromVendorProperties(circuitProperties, &circuitId));

    AcxCircuitInitSetComponentId(CircuitInit, &circuitId);

    // Call the appropriate CreateCircuitDevice based on the Circuit ID
    if (IsEqualGUID(circuitId, DSP_CIRCUIT_MICROPHONE_GUID) || IsEqualGUID(circuitId, DSP_CIRCUIT_UNIVERSALJACK_CAPTURE_GUID))
    {
        return DspC_EvtAcxFactoryCircuitCreateCircuit(Parent, Device, Factory, CircuitConfig, CircuitInit);
    }
    else if (IsEqualGUID(circuitId, DSP_CIRCUIT_SPEAKER_GUID) || IsEqualGUID(circuitId, DSP_CIRCUIT_UNIVERSALJACK_RENDER_GUID))
    {
        return DspR_EvtAcxFactoryCircuitCreateCircuit(Parent, Device, Factory, CircuitConfig, CircuitInit);
    }

    status = STATUS_NOT_SUPPORTED;
    return status;
}
```

## -see-also

[acxcircuit.h header](index.md)

