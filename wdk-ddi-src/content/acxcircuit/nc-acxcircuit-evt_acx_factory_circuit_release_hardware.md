---
UID: NC:acxcircuit.EVT_ACX_FACTORY_CIRCUIT_RELEASE_HARDWARE
tech.root: audio
title: EVT_ACX_FACTORY_CIRCUIT_RELEASE_HARDWARE
ms.date: 08/23/2021
targetos: Windows
description: TBD - The EVT_ACX_FACTORY_CIRCUIT_RELEASE_HARDWARE callback is used by the driver to allow it to add additional functionality when a circuit factory is in the release hardware phase, using the TBD function is called,  TBD TBD. 
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
 - EVT_ACX_FACTORY_CIRCUIT_RELEASE_HARDWARE
f1_keywords:
 - EVT_ACX_FACTORY_CIRCUIT_RELEASE_HARDWARE
 - acxcircuit/EVT_ACX_FACTORY_CIRCUIT_RELEASE_HARDWARE
dev_langs:
 - c++
---

## -description

TBD - The EVT_ACX_FACTORY_CIRCUIT_RELEASE_HARDWARE callback is used by the driver to allow it to add additional functionality when a circuit factory is in the release hardware phase, using the TBD function is called,  TBD TBD. 

## -parameters

### -param Device

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that TBD has/is will be the parent under these conditions - TBD TBD 

### -param Factory

### -param ResourcesTranslated

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp

```

## -see-also

[acxcircuit.h header](index.md)

