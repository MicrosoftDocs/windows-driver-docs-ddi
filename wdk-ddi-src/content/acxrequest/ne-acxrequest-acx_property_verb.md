---
UID: NE:acxrequest._ACX_PROPERTY_VERB
tech.root: audio
title: ACX_PROPERTY_VERB
ms.date: 07/26/2022
targetos: Windows
description: The ACX_PROPERTY_VERB enumeration describes the type of verb operations suppored on ACX properties. 
prerelease: true
req.construct-type: enumeration
req.ddi-compliance: 
req.header: acxrequest.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxrequest.h
api_name:
 - _ACX_PROPERTY_VERB
 - PACX_PROPERTY_VERB
 - ACX_PROPERTY_VERB
f1_keywords:
 - _ACX_PROPERTY_VERB
 - acxrequest/_ACX_PROPERTY_VERB
 - PACX_PROPERTY_VERB
 - acxrequest/PACX_PROPERTY_VERB
 - ACX_PROPERTY_VERB
 - acxrequest/ACX_PROPERTY_VERB
dev_langs:
 - c++
---

## -description

The **ACX_PROPERTY_VERB** enumeration describes the type of verb operations suppored on ACX properties.

## -enum-fields

### -field AcxPropertyVerbNone

No verb support.

### -field AcxPropertyVerbGet

Get Verb Support is enabled.

### -field AcxPropertyVerbSet

Set Verb Support is enabled.

### -field AcxPropertyVerbBasicSupport

Basic Verb support is available.

### -field AcxPropertyVerbSetSupport

Verb Set support is available.

### -field AcxPropertyVerbMax

For internal validation, do not use.

## -remarks

### Example

Example usage is shown below.

```cpp
(
    _In_ WDFDEVICE Device,
    _In_ ACXTARGETCIRCUIT TargetCircuit,
    _In_ GUID PropertySet,
    _In_ ULONG PropertyId,
    _In_ ACX_PROPERTY_VERB Verb,
    _Inout_ PVOID Value,
    _In_ ULONG ValueCb
)
{
    PAGED_CODE();

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

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxrequest.h header](index.md)
