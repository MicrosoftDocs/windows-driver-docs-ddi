---
UID: NC:acxcircuit.EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUITDEVICE
tech.root: audio
title: EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUITDEVICE
ms.date: 08/24/2021
targetos: Windows
description: The EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUITDEVICE callback is invoked by ACX when the driver must create a WDFDEVICE for a new ACXCIRCUIT object.
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
 - EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUITDEVICE
f1_keywords:
 - EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUITDEVICE
 - acxcircuit/EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUITDEVICE
dev_langs:
 - c++
---

## -description

The EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUITDEVICE callback is invoked by ACX when the driver must create a WDFDEVICE for a new ACXCIRCUIT object.

## -parameters

### -param Parent

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that is the parent of the WDFDEVICE referenced in Device object.

### -param Factory
 
The existing circuit factory ACXFACTORYCIRCUIT Object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Config

An [ACX_FACTORY_CIRCUIT_ADD_CIRCUIT](ns-acxcircuit-acx_factory_circuit_add_circuit.md) structure that defines the configuration for the new ACXCIRCUIT.

### -param Device

A pointer to a location that receives a handle to the new  WDFDEVICE framework object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)). 

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).


## -remarks

An AcxFactoryCircuit represents a factory object capable of creating an ACXCIRCUIT on demand. 
A driver can register one or more ACXFACTORYCIRCUIT with ACX, this action let ACX know that the driver is capabile of creating ACXCIRCUITs of a well defined type.
ACX invokes the ACXFACTORYCIRCUIT's callbacks when it detects that an audio path requires one of the factory provided ACXCIRCUITs.

The ACXFACTORYCIRCUIT object supports dynamic ACXCIRCUITs, this means that each ACXCIRCUIT created by the factory is associated with a WDFDEVICE and these two objects have the same lifetime.

An AcxFactoryCircuit has a dedicated WDF queue. For more information about WDF queues, see [Framework Queue Objects](/windows-hardware/drivers/wdf/framework-queue-objects)

### Example

Example usage is shown below.

```cpp
NTSTATUS
Dsp_EvtAcxFactoryCircuitCreateCircuitDevice(
    _In_  WDFDEVICE                         Parent,
    _In_  ACXFACTORYCIRCUIT                 Factory,
    _In_  PACX_FACTORY_CIRCUIT_ADD_CIRCUIT  CircuitConfig,
    _Out_ WDFDEVICE* Device
)
{
    ACXOBJECTBAG circuitProperties;

    PAGED_CODE();

    NTSTATUS status = STATUS_SUCCESS;
    WDF_OBJECT_ATTRIBUTES attributes;

    *Device = NULL;

    // Create object bag from the CircuitProperties
    ACX_OBJECTBAG_CONFIG propConfig;
    ACX_OBJECTBAG_CONFIG_INIT(&propConfig);
    propConfig.Handle = CircuitConfig->CircuitProperties;
    propConfig.Flags |= AcxObjectBagConfigOpenWithHandle;

    WDF_OBJECT_ATTRIBUTES_INIT(&attributes);

    RETURN_NTSTATUS_IF_FAILED(AcxObjectBagOpen(&attributes, &propConfig, &circuitProperties));

    auto cleanupPropConfig = scope_exit([=]() {
        WdfObjectDelete(circuitProperties);
        }
    );

    // Retrieve the intended Circuit ID from the object bag
    GUID circuitId;
    RETURN_NTSTATUS_IF_FAILED(Dsp_DetermineCircuitGuidFromVendorProperties(circuitProperties, &circuitId));

    // Call the appropriate CreateCircuitDevice based on the Circuit ID
    if (IsEqualGUID(circuitId, DSP_CIRCUIT_MICROPHONE_GUID) || IsEqualGUID(circuitId, DSP_CIRCUIT_UNIVERSALJACK_CAPTURE_GUID))
    {
        return DspC_EvtAcxFactoryCircuitCreateCircuitDevice(Parent, Factory, CircuitConfig, Device);
    }
    else if (IsEqualGUID(circuitId, DSP_CIRCUIT_SPEAKER_GUID) || IsEqualGUID(circuitId, DSP_CIRCUIT_UNIVERSALJACK_RENDER_GUID))
    {
        return DspR_EvtAcxFactoryCircuitCreateCircuitDevice(Parent, Factory, CircuitConfig, Device);
    }

    status = STATUS_NOT_SUPPORTED;
    DrvLogError(g_SDCAVDspLog, FLAG_INIT, L"Unexpected CircuitId %!GUID!, %!STATUS!", &circuitId, status);
    return status;
}


```

## -see-also

[acxcircuit.h header](index.md)

READY2GO