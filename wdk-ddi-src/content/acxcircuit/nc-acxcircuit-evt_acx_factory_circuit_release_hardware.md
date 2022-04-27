---
UID: NC:acxcircuit.EVT_ACX_FACTORY_CIRCUIT_RELEASE_HARDWARE
tech.root: audio
title: EVT_ACX_FACTORY_CIRCUIT_RELEASE_HARDWARE
ms.date: 02/01/2022
targetos: Windows
description: The EVT_ACX_FACTORY_CIRCUIT_RELEASE_HARDWARE callback is used by the driver to allow it to add additional functionality when a circuit factory is in the release hardware phase. 
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

The EVT_ACX_FACTORY_CIRCUIT_RELEASE_HARDWARE callback is used by the driver to allow it to add additional functionality when a circuit factory is in the release hardware phase. 

## -parameters

### -param Device

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that is associated with the ACX circuit.

### -param Factory

The existing circuit factory ACXFACTORYCIRCUIT Object. (For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param ResourcesTranslated

A WDF resource list that describes the translated resources to be used for the prepare hardware phase TBD. This is a WDF framework resource-list object that represents a list of hardware resources for a device. For more information about translated resource lists, see [Raw and Translated Resources](/windows-hardware/drivers/wdf/hardware-resources-for-kmdf-drivers).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

Sample pending.

```cpp

```

## -see-also

- [acxcircuit.h header](index.md)

TBD - Please review this topic