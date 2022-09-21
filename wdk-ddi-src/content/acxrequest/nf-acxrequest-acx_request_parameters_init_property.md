---
UID: NF:acxrequest.ACX_REQUEST_PARAMETERS_INIT_PROPERTY
tech.root: audio
title: ACX_REQUEST_PARAMETERS_INIT_PROPERTY
ms.date: 07/26/2022
targetos: Windows
description: The ACX_REQUEST_PARAMETERS_INIT_PROPERTY initializes an ACX_REQUEST_PARAMETERS struct with ACX property parameters.
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

The **ACX_REQUEST_PARAMETERS_INIT_PROPERTY** initializes an ACX_REQUEST_PARAMETERS struct with ACX property parameters.

## -parameters

### -param Params

A pointer to [ACX_REQUEST_PARAMETERS](ns-acxrequest-acx_request_parameters.md) structure that is used to store property parameters.

### -param Set

A property Set ID (GUID).

### -param Id

A property ID (ULONG) within the property Set ID.

### -param Verb

The ACX property verb to send as defined by the [ACX_PROPERTY_VERB](ne-acxrequest-acx_property_verb.md) enumeration.

### -param ItemType

The [ACX_ITEM_TYPE](ne-acxrequest-acx_item_type.md) type of item being sent, for example AcxItemTypeCircuit.

### -param ItemId

The item ID of the ItemType, for example the pin ID if the ItemType is a pin.

### -param Control

An optional Control buffer holding additional parameters for the specified property. Set to null if not present.

### -param ControlCb

The count in bytes (size) of the Control buffer. Set to 0 if Control field is not used.

### -param Value

An optional Value buffer to specify or receive the property's value. Set to null if not present or if *SendProperty needs to allocate it when ValueCb is not zero. Caller is responsible for freeing the allocated buffer.

### -param ValueCb

The count in bytes (size) of the Value buffer. Set to 0 if Value is not used.

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

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxrequest.h header](index.md)
