---
UID: NC:acxcircuit.EVT_ACX_CIRCUIT_COMPOSITE_CIRCUIT_INITIALIZE
tech.root: audio
title: EVT_ACX_CIRCUIT_COMPOSITE_CIRCUIT_INITIALIZE
ms.date: 09/30/2021
targetos: Windows
description: The EVT_ACX_CIRCUIT_COMPOSITE_CIRCUIT_INITIALIZE callback is used by the driver to do any initialization of a composite circuit when it is detected and initialized by ACX Manager. 
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

The **EVT_ACX_CIRCUIT_COMPOSITE_CIRCUIT_INITIALIZE** callback is used by the driver to do any initialization of a composite circuit when it is detected and initialized by ACX Manager. 

## -parameters

### -param Device

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that is associated with the specified ACXCIRCUIT. 

### -param Circuit

The ACXCIRCUIT object being initialized.  For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects). 

### -param CircuitProperties

Optional handle to CircuitProperties. This is an optional ACXOBJECTBAG object for ACXCIRCUIT's properties. 

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

This sample code shows how the driver retrieves a circuit property from the specified circuit property object bag.

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
            // Log error.
            goto exit;
        }

        //...
    }
    
    //...

    // All done.
    status = STATUS_SUCCESS;

exit:
    return status;
}
```

## -see-also

- [acxcircuit.h header](index.md)

READY2GO

EDITCOMPLETE
