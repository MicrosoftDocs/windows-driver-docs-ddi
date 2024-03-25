---
UID: NC:acxcircuit.EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUIT
tech.root: audio
title: EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUIT
ms.date: 12/14/2022
targetos: Windows
description: The EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUIT callback is invoked by ACX when the driver must create an ACXCIRCUIT object with the specified configuration.
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

The **EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUIT** callback is invoked by ACX when the driver must create an ACXCIRCUIT object with the specified configuration.

## -parameters

### -param Parent

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that is the parent of the WDFDEVICE referenced in Device object.

### -param Device

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) created in the EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUITDEVICE callback. This device will be associated with the new ACXCIRCUIT.

### -param Factory

The existing circuit factory ACXFACTORYCIRCUIT Object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Config

An [ACX_FACTORY_CIRCUIT_ADD_CIRCUIT](ns-acxcircuit-acx_factory_circuit_add_circuit.md) structure that defines the configuration for the new ACXCIRCUIT.

### -param CircuitInit

ACXCIRCUIT_INIT is an opaque object used for circuit initialization. Use [AcxCircuitInitAllocate](nf-acxcircuit-acxcircuitinitallocate.md) to initialize the ACXCIRCUIT_INIT structure.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

An AcxFactoryCircuit represents a factory object capable of creating an ACXCIRCUIT on demand.

A driver can register one or more ACXFACTORYCIRCUIT with ACX, this action will let ACX know that the driver is capable of creating ACXCIRCUITs of a well defined type.

ACX invokes the ACXFACTORYCIRCUIT's callbacks when it detects that an audio path requires one of the factory provided ACXCIRCUITs.

An AcxFactoryCircuit has a dedicated WDF queue. For more information about WDF queues, see [Framework Queue Objects](/windows-hardware/drivers/wdf/framework-queue-objects).

### Example

Example usage is shown below.

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

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxcircuit.h header](index.md)
