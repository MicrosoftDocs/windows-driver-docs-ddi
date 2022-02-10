---
UID: NF:acxrequest.ACX_REQUEST_PARAMETERS_INIT_PROPERTY
tech.root: audio
title: ACX_REQUEST_PARAMETERS_INIT_PROPERTY
ms.date: 02/07/2022
targetos: Windows
description: The ACX_REQUEST_PARAMETERS_INIT_PROPERTY initializes ACX request parameter properties.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxrequest.h
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
 - acxrequest.h
api_name:
 - ACX_REQUEST_PARAMETERS_INIT_PROPERTY
f1_keywords:
 - ACX_REQUEST_PARAMETERS_INIT_PROPERTY
 - acxrequest/ACX_REQUEST_PARAMETERS_INIT_PROPERTY
dev_langs:
 - c++
---

## -description

The **ACX_REQUEST_PARAMETERS_INIT_PROPERTY** function initializes ACX request parameter properties.

## -parameters

### -param Params

An initialized [ACX_REQUEST_PARAMETERS](ns-acxrequest-acx_request_parameters.md) structure that is used to store circuit information.

### -param Set

A set of Methods that are TBD.

### -param Id

The Method ID that will be TBD.

### -param Verb

The Acx Method Verb to send as defined by the [ACX_PROPERTY_VERB](ne-acxrequest-acx_property_verb.md) enumeration.

### -param ItemType

The [ACX_ITEM_TYPE](ne-acxrequest-acx_item_type.md) type of item being sent, for example AcxItemTypeCircuit.

### -param ItemId

TDB - An Item Id, for example for a pin number in a circuit.

### -param Control

A Control that TBD.

### -param ControlCb

The count in bytes (size) of the Control.
 
### -param Value

The  value that will be TBD. TBD - Provide a null Value so that the SendProperty will allocate it. Make sure that the allocated value is freed.

### -param ValueCb

The count in bytes (size) of the Value.

## -remarks

### Example

Example usage is shown below.

```cpp
    NTSTATUS                    status = STATUS_SUCCESS;
    PKSPIN_PHYSICALCONNECTION   physicalConnection = nullptr;
    PAUDIO_PATH_DESCRIPTOR      descriptor = nullptr;

    // For the Audio Circuit, send a request to each Target Pin asking KSPROPERTY_PIN_PHYSICALCONNECTION
    // This will give us symbolic link of the next circuit in the Audio Path (if there is any)

    for (ULONG i = 0; i < ARRAYSIZE(AudioCircuit->Pins) && AudioCircuit->Pins[i].TargetPin; ++i)
    {
        ACX_REQUEST_PARAMETERS requestParams{ 0 };

        ACX_REQUEST_PARAMETERS_INIT_PROPERTY(
            &requestParams,
            KSPROPSETID_Pin,
            KSPROPERTY_PIN_PHYSICALCONNECTION,
            AcxPropertyVerbGet,
            AcxItemTypePin,
            i,
            nullptr,
            0,
            // null Value so SendProperty will allocate it for us. We'll need to free it.
            nullptr,
            0);
...
```

## -see-also

