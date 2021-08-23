---
UID: NC:acxcircuit.EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUITDEVICE
tech.root: audio
title: EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUITDEVICE
ms.date: 08/23/2021
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
 - EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUITDEVICE
f1_keywords:
 - EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUITDEVICE
 - acxcircuit/EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUITDEVICE
dev_langs:
 - c++
---

## -description

The EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUITDEVICE callback is used by the driver to allow it to add addtional functionality when the TBD function is called,  TBD TBD.

This callback is located in the acxcircuit header.

## -parameters

### -param Parent

WDFDEVICE Parent

### -param Factory
 
A pointer to a location that receives (TBD??) a handle to the new ACXFACTORYCIRCUIT Object. (DocsTeam - need link to ACX Object Summary topic).

### -param Config

PACX_FACTORY_CIRCUIT_ADD_CIRCUIT Config,


### -param Device

A pointer to a location that receives a handle to the new framework device object.

## -returns



## -remarks

An AcxFactoryCircuits represents a partial audio path to a user perceived audio device (speakers, mic, etc.). 
An AcxFactoryCircuits aggregates zero or ‘n’ AcxElements-like objects. By default, AcxElements are ‘connected’ in the same order of assembly. 

An AcxCircuit has a dedicated WDF queue. For more information about WDF queues, see [Framework Queue Objects](/windows-hardware/drivers/wdf/framework-queue-objects)

### Example

TBD - No sample code found

Example usage is shown below.

```cpp

```

## -see-also

[acxcircuit.h header](index.md)

