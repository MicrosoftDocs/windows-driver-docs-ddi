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

### -param Set

### -param Id

### -param Verb

### -param ItemType

### -param ItemId

### -param Control

### -param ControlCb

### -param Value

### -param ValueCb

## -remarks

### Example

Example usage is shown below.

```cpp

    _In_ ACXTARGETCIRCUIT TargetCircuit,
    _In_ GUID PropertySet,
    _In_ ULONG PropertyId,
    _In_ ACX_PROPERTY_VERB Verb,
    _Inout_ PVOID Value,
    _In_ ULONG ValueCb
)
{

    ACX_REQUEST_PARAMETERS requestParams;

    ACX_REQUEST_PARAMETERS_INIT_PROPERTY(
        &requestParams,
        PropertySet,
        PropertyId,
        Verb,
        AcxItemTypeCircuit,
        0,
        NULL, 0,
        Value, ValueCb
    );


```

## -see-also

