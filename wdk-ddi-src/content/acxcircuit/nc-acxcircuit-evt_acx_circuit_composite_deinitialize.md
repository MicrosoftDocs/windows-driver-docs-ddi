---
UID: NC:acxcircuit.EVT_ACX_CIRCUIT_COMPOSITE_DEINITIALIZE
tech.root: audio
title: EVT_ACX_CIRCUIT_COMPOSITE_DEINITIALIZE
ms.date: 12/14/2022
targetos: Windows
description: The EVT_ACX_CIRCUIT_COMPOSITE_CIRCUIT_DEINITIALIZE callback is used by the driver to do any de-initialiation of a composite circuit when it is de-initialized by ACX Manager.
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
 - EVT_ACX_CIRCUIT_COMPOSITE_DEINITIALIZE
f1_keywords:
 - EVT_ACX_CIRCUIT_COMPOSITE_DEINITIALIZE
 - acxcircuit/EVT_ACX_CIRCUIT_COMPOSITE_DEINITIALIZE
dev_langs:
 - c++
---

## -description

The **EVT_ACX_CIRCUIT_COMPOSITE_CIRCUIT_DEINITIALIZE** callback is used by the driver to do any de-initialiation of a composite circuit when it is de-initialized by ACX Manager.

## -parameters

### -param Device

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that is associated with the specified ACXCIRCUIT.

### -param Circuit

The ACXCIRCUIT object being de-initialized. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param CompositeProperties

Optional handle to CircuitProperties. This is an optional ACXOBJECTBAG object for ACXCIRCUIT's properties.

## -remarks

ACX is able to invoke this callback for a composite ACXCIRCUIT only if the associated WDFDEVICE is present. That is, if the associated WDFDEVICE is surprise-removed (SR), ACX will not be able to invoke the callback because its associated PnP interfaces are turned off.

### Example

This sample code shows how the driver retrieves a circuit property from the specified circuit property object bag.

Example usage is shown below.

```cpp
VOID
DspR_EvtCircuitCompositeDeinitialize(
    _In_     WDFDEVICE      Device,
    _In_     ACXCIRCUIT     Circuit,
    _In_opt_ ACXOBJECTBAG   CompositeProperties
    )
{
    DECLARE_CONST_ACXOBJECTBAG_SYSTEM_PROPERTY_NAME(UniqueID);
    NTSTATUS    status      = STATUS_SUCCESS;
    GUID        uniqueId    = {0};

    PAGED_CODE();

    UNREFERENCED_PARAMETER(Device);
    UNREFERENCED_PARAMETER(Circuit);

    if (CompositeProperties)
    {
        status = AcxObjectBagRetrieveGuid(CompositeProperties, &UniqueID, &uniqueId);
        if (!NT_SUCCESS(status))
        {
            // Log error.
        }
    }
}
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxcircuit.h header](index.md)
