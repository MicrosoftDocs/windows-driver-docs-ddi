---
UID: NC:acxcircuit.EVT_ACX_CIRCUIT_COMPOSITE_CIRCUIT_INITIALIZE
tech.root: audio
title: EVT_ACX_CIRCUIT_COMPOSITE_CIRCUIT_INITIALIZE
ms.date: 08/20/2021
targetos: Windows
description: 
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
 - EVT_ACX_CIRCUIT_COMPOSITE_CIRCUIT_INITIALIZE
f1_keywords:
 - EVT_ACX_CIRCUIT_COMPOSITE_CIRCUIT_INITIALIZE
 - acxcircuit/EVT_ACX_CIRCUIT_COMPOSITE_CIRCUIT_INITIALIZE
dev_langs:
 - c++
---

## -description

The EVT_ACX_CIRCUIT_COMPOSITE_CIRCUIT_INITIALIZE callback is used by the driver to allow it to add additional functionality when a composite circuit is initialized using the TBD function is called,  TBD TBD. The Circuit object bag will contain TBD that can be used for TBD.

## -parameters

### -param Device

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that TBD has/is will be the parent under these conditions - TBD TBD 

### -param Circuit

TBD - An existing ACXCIRCUIT circuit object.  (DocsTeam - need link to ACX Object Summary topic).

### -param CircuitProperties

TBD - Optional handle to CircuitProperties. This is an existing ACXOBJECTBAG circuit object properties.  (DocsTeam - need link to ACX Object Summary topic).

ACXOBJECTBAG CircuitProperties


## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.


TBD TBD TBD

TBD - This sample code just seems to be showing how to get the object bag, but then doesn't do anything with it?

TBD TBD TBD 

```cpp
DspR_EvtCircuitCompositeCircuitInitialize(
    _In_     WDFDEVICE      Device,
    _In_     ACXCIRCUIT     Circuit,
    _In_opt_ ACXOBJECTBAG   CircuitProperties
    )
{
    NTSTATUS status = STATUS_SUCCESS;

    PAGED_CODE();
    
    UNREFERENCED_PARAMETER(Device);
    UNREFERENCED_PARAMETER(Circuit);

    if (CircuitProperties != NULL)
    {
        DECLARE_CONST_ACXOBJECTBAG_DRIVER_PROPERTY_NAME(msft, TestUI4);
        ULONG testUI4;

        status = AcxObjectBagRetrieveUI4(CircuitProperties, &TestUI4, &testUI4);
        if (!NT_SUCCESS(status))
        {
            ASSERT(FALSE);
            goto exit;
        }
    }
    
    // All done.
    status = STATUS_SUCCESS;

exit:
    return status;
}


```

## -see-also

[acxcircuit.h header](index.md)

