---
UID: NC:acxcircuit.EVT_ACX_FACTORY_CIRCUIT_POWER_UP
tech.root: audio
title: EVT_ACX_FACTORY_CIRCUIT_POWER_UP
ms.date: 02/01/2022
targetos: Windows
description: The EVT_ACX_FACTORY_CIRCUIT_POWER_UP callback is used by the driver to allow it to add additional functionality when a factory circuit is powered up. 
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
 - EVT_ACX_FACTORY_CIRCUIT_POWER_UP
f1_keywords:
 - EVT_ACX_FACTORY_CIRCUIT_POWER_UP
 - acxcircuit/EVT_ACX_FACTORY_CIRCUIT_POWER_UP
dev_langs:
 - c++
---

## -description

The EVT_ACX_FACTORY_CIRCUIT_POWER_UP callback is used by the driver to allow it to add additional functionality when a factory circuit is powered up. 

## -parameters

### -param Device

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that is associated with the ACX circuit.

### -param Factory

The existing circuit factory ACXFACTORYCIRCUIT Object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param PreviousState

A [WDF_POWER_DEVICE_STATE enumeration](/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_power_device_state) that identifies the previous device power state.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

TBD - No example code or unit tests found.

```cpp

```

## -see-also

[acxcircuit.h header](index.md)

TBD - Please review this topic