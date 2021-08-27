---
UID: NC:acxcircuit.EVT_ACX_CIRCUIT_COMPOSITE_DEINITIALIZE
tech.root: audio
title: EVT_ACX_CIRCUIT_COMPOSITE_DEINITIALIZE
ms.date: 08/24/2021
targetos: Windows
description: TBD - The EVT_ACX_CIRCUIT_COMPOSITE_CIRCUIT_DEINITIALIZE callback is used by the driver to allow it to add additional functionality when a composite circuit is de-initialized using the TBD function is called,  TBD TBD.
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
 - EVT_ACX_CIRCUIT_COMPOSITE_DEINITIALIZE
f1_keywords:
 - EVT_ACX_CIRCUIT_COMPOSITE_DEINITIALIZE
 - acxcircuit/EVT_ACX_CIRCUIT_COMPOSITE_DEINITIALIZE
dev_langs:
 - c++
---

## -description

TBD - The EVT_ACX_CIRCUIT_COMPOSITE_CIRCUIT_DEINITIALIZE callback is used by the driver to allow it to add additional functionality when a composite circuit is de-initialized using the TBD function is called,  TBD TBD. The circuit object bag will contain TBD that can be used by the driver for TBD. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -parameters

### -param Device

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that TBD has/is will be the parent under these conditions - TBD TBD 

### -param Circuit

TBD - An existing ACXCIRCUIT circuit object. 

### -param CompositeProperties

TBD - Optional handle to CircuitProperties that describes the composite circuit. This is an existing ACXOBJECTBAG circuit object properties.  

## -remarks

### Example

TBD TBD TBD

TBD - This sample code just seems to be showing how to get the object bag, but then doesn't do anything with it?

TBD TBD TBD 

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
            ASSERT(FALSE);
        }
    }
}
```

## -see-also

[acxcircuit.h header](index.md)

