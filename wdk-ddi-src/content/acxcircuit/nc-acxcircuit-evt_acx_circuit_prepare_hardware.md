---
UID: NC:acxcircuit.EVT_ACX_CIRCUIT_PREPARE_HARDWARE
tech.root: audio
title: EVT_ACX_CIRCUIT_PREPARE_HARDWARE
ms.date: 08/23/2021
targetos: Windows
description: TBD - The EVT_ACX_CIRCUIT_PREPARE_HARDWARE callback is used by the driver to allow it to add additional functionality when a circuit is in the prepare hardware phase, using the TBD function is called,  TBD TBD. 
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
 - EVT_ACX_CIRCUIT_PREPARE_HARDWARE
f1_keywords:
 - EVT_ACX_CIRCUIT_PREPARE_HARDWARE
 - acxcircuit/EVT_ACX_CIRCUIT_PREPARE_HARDWARE
dev_langs:
 - c++
---

## -description

TBD - The EVT_ACX_CIRCUIT_PREPARE_HARDWARE callback is used by the driver to allow it to add additional functionality when a circuit is in the prepare hardware phase, using the TBD function is called,  TBD TBD. 

## -parameters

### -param Device

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that TBD has/is will be the parent under these conditions - TBD TBD 

### -param Circuit

TBD - An existing ACXCIRCUIT circuit object.  (DocsTeam - need link to ACX Object Summary topic).

### -param ResourcesRaw

A WDF resource list that describes the raw resources to be used for the prepare hardware phase TBD TBD. This is a WDF framework resource-list object that represents a list of hardware resources for a device. For more information about raw resources, see [Hardware Resources for Framework-Based Drivers](/windows-hardware/drivers/wdf/raw-and-translated-resources).

### -param ResourcesTranslated

A WDF resource list that describes the translated resources to be used for the prepare hardware phase TBD TBD. This is a WDF framework resource-list object that represents a list of hardware resources for a device. For more information about translated resource lists, see [Raw and Translated Resources](/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

TBD - Do we have any hardware sample code we can use here with and actual resource list?

```cpp
NTSTATUS
EvtCircuitPrepareHardware(
    _In_ WDFDEVICE      Device,
    _In_ ACXCIRCUIT     Circuit,
    _In_ WDFCMRESLIST   ResourcesRaw,
    _In_ WDFCMRESLIST   ResourcesTranslated
    )
{
    NTSTATUS            status      = STATUS_SUCCESS;
    PCIRCUIT_CONTEXT    circuitCtx  = GetCircuitContext(Circuit);
    CIpcEventReader *   eventReader = circuitCtx->EventReader;

    PASSIVE_CODE();

    UNREFERENCED_PARAMETER(Device);
    UNREFERENCED_PARAMETER(ResourcesRaw);
    UNREFERENCED_PARAMETER(ResourcesTranslated);

    //
    // Enable 'remote' circuit notifications.
    //
    ASSERT(eventReader);
    status = eventReader->EnableEvents();
    if (!NT_SUCCESS(status))
    {
        DrvLogError(g_RecorderLog, FLAG_INIT,
                    "ACXCIRCUIT %p, CIpcEventReader::EnableEvents failed, %!STATUS!",
                    Circuit, status);
        goto exit;
    }

    status = STATUS_SUCCESS;

exit:
    return status;
}
```

## -see-also

[acxcircuit.h header](index.md)

