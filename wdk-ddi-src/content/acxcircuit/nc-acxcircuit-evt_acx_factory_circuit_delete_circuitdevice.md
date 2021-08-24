---
UID: NC:acxcircuit.EVT_ACX_FACTORY_CIRCUIT_DELETE_CIRCUITDEVICE
tech.root: audio
title: EVT_ACX_FACTORY_CIRCUIT_DELETE_CIRCUITDEVICE
ms.date: 08/24/2021
targetos: Windows
description: TBD - The EVT_ACX_FACTORY_CIRCUIT_DELETE_CIRCUITDEVICE callback is used by the driver to allow it to add additional functionality when the TBD function is called,  and an acx circuit device is deleted, TBD TBD.
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
 - EVT_ACX_FACTORY_CIRCUIT_DELETE_CIRCUITDEVICE
f1_keywords:
 - EVT_ACX_FACTORY_CIRCUIT_DELETE_CIRCUITDEVICE
 - acxcircuit/EVT_ACX_FACTORY_CIRCUIT_DELETE_CIRCUITDEVICE
dev_langs:
 - c++
---

## -description

TBD - The EVT_ACX_FACTORY_CIRCUIT_DELETE_CIRCUITDEVICE callback is used by the driver to allow it to add additional functionality when the TBD function is called,  and an acx circuit device is deleted, TBD TBD.

## -parameters

### -param Factory

TBD - The existing circuit factory ACXFACTORYCIRCUIT Object. (DocsTeam - need link to ACX Object Summary topic).

### -param Device

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that TBD has/is will be the parent under these conditions - TBD TBD 

TBD - Is there a second WDFDEVICE Device param?

```cpp
EVT_ACX_FACTORY_CIRCUIT_DELETE_CIRCUITDEVICE(
    _In_
    WDFDEVICE Parent,
    _In_
    ACXFACTORYCIRCUIT Factory,
    _In_
    WDFDEVICE Device
```

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

