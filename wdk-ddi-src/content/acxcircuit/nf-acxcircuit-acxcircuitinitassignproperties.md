---
UID: NF:acxcircuit.AcxCircuitInitAssignProperties
tech.root: audio
title: AcxCircuitInitAssignProperties
ms.date: 12/14/2022
targetos: Windows
description: The AcxCircuitInitAssignProperties function assigns one or more ACX properties for the ACXCIRCUIT.
prerelease: true
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
 - AcxCircuitInitAssignProperties
f1_keywords:
 - AcxCircuitInitAssignProperties
 - acxcircuit/AcxCircuitInitAssignProperties
dev_langs:
 - c++
---

## -description

The **AcxCircuitInitAssignProperties** function assigns one or more ACX properties for the ACXCIRCUIT.

## -parameters

### -param CircuitInit

The ACXCIRCUIT_INIT structure that defines the circuit initialization. ACXCIRCUIT_INIT is an opaque object used for circuit initialization. Use [AcxCircuitInitAllocate](nf-acxcircuit-acxcircuitinitallocate.md) to initialize the ACXCIRCUIT_INIT structure.

### -param Properties

An [ACX_PROPERTY_ITEM structure](/windows-hardware/drivers/ddi/acxrequest/ns-acxrequest-acx_property_item) that defines a set of properties that will be used for circuit initialization by the circuit factory.

### -param PropertiesCount

The number of properties that will be added to the circuit. This is a one based count.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

Drivers should only add driver owned properties.

### Example

Example usage is shown below.

```cpp

    PACXCIRCUIT_INIT circuitInit = NULL;
    circuitInit = AcxCircuitInitAllocate(Device);

    ACX_PROPERTY_ITEM CircuitProperties[] =
    {
        {
            &KSPROPSETID_AudioPosture,
            KSPROPERTY_AUDIOPOSTURE_ORIENTATION,
            KSPROPERTY_TYPE_SET,
            EvtCircuitPropertyHandler,
            nullptr,                            //Reserved
            0,                                  //ControlCb
            sizeof(AUDIOPOSTURE_ORIENTATION),   //ValueCb
        },
    };


    status = AcxCircuitInitAssignProperties(circuitInit,
        CircuitProperties,
        SIZEOF_ARRAY(CircuitProperties));
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxcircuit.h header](index.md)
