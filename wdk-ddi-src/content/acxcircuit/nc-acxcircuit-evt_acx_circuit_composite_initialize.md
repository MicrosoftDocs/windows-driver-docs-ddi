---
UID: NC:acxcircuit.EVT_ACX_CIRCUIT_COMPOSITE_INITIALIZE
tech.root: audio
title: EVT_ACX_CIRCUIT_COMPOSITE_INITIALIZE
ms.date: 12/14/2022
targetos: Windows
description: The EVT_ACX_CIRCUIT_COMPOSITE_INITIALIZE callback is used by the driver to do any post-initialization after the composite endpoint has been assembled by ACX Manager.
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
 - EVT_ACX_CIRCUIT_COMPOSITE_INITIALIZE
f1_keywords:
 - EVT_ACX_CIRCUIT_COMPOSITE_INITIALIZE
 - acxcircuit/EVT_ACX_CIRCUIT_COMPOSITE_INITIALIZE
dev_langs:
 - c++
---

## -description

The **EVT_ACX_CIRCUIT_COMPOSITE_INITIALIZE** callback is used by the driver to do any post-initialization after the composite endpoint has been assembled by ACX Manager.

## -parameters

### -param Device

A WDFDEVICE object (described in [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that is associated with the specified ACXCIRCUIT.

### -param Circuit

The ACXCIRCUIT object being initialized. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param CompositeProperties

Optional handle to CompositeProperties that describes the composite circuit. This is an optional ACXOBJECTBAG object for composite endpoint's properties.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

This sample code shows how the driver retrieves a composite property from the specified composite property object bag.

```cpp
EVT_ACX_CIRCUIT_COMPOSITE_INITIALIZE CodecR_EvtCircuitCompositeInitialize;

NTSTATUS
CodecR_EvtCircuitCompositeInitialize(
    _In_ WDFDEVICE      Device,
    _In_ ACXCIRCUIT     Circuit,
    _In_ ACXOBJECTBAG   CompositeProperties
    )
{
    PAGED_CODE();

    NTSTATUS status = STATUS_SUCCESS;

    UNREFERENCED_PARAMETER(Device);
    UNREFERENCED_PARAMETER(Circuit);

    ASSERT(CompositeProperties);

    DECLARE_CONST_ACXOBJECTBAG_SYSTEM_PROPERTY_NAME(UniqueID);
    GUID uniqueId = {0};
    status = AcxObjectBagRetrieveGuid(CompositeProperties, &UniqueID, &uniqueId);

    // ...

    return status;
}
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxcircuit.h header](index.md)
