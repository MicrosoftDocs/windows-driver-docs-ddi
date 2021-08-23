---
UID: NC:acxcircuit.EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUIT
tech.root: audio
title: EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUIT
ms.date: 
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
 - EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUIT
f1_keywords:
 - EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUIT
 - acxcircuit/EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUIT
dev_langs:
 - c++
---

## -description

The EVT_ACX_FACTORY_CIRCUIT_CREATE_CIRCUIT callback is used by the driver to This function is located in the acxcircuit header.



## -parameters

### -param Parent
  WDFDEVICE Parent,

### -param Device

  WDFDEVICE Device,

A pointer to a location that receives a handle to the new framework device object.

A WDFDEVICE object (described in  [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that TBD has/is will be the parent under these conditions - TBD TBD 

### -param Factory

  ACXFACTORYCIRCUIT Factory,

### -param Config

  PACX_FACTORY_CIRCUIT_ADD_CIRCUIT Config,

### -param CircuitInit

TBD- The ACXCIRCUIT_INIT structure that defines the circuit initialization. ACXCIRCUIT_INIT is an opaque object used for circuit initialization. Use [AcxCircuitInitAllocate](nf-acxcircuit-acxcircuitinitallocate.md) to initialize the ACXCIRCUIT_INIT structure.

## -returns

TBD

## -remarks

An AcxFactoryCircuits represents a partial audio path to a user perceived audio device (speakers, mic, etc.). 
An AcxFactoryCircuits aggregates zero or ‘n’ AcxElements-like objects. By default, AcxElements are ‘connected’ in the same order of assembly. 

An AcxCircuit has a dedicated WDF queue. For more information about WDF queues, see [Framework Queue Objects](/windows-hardware/drivers/wdf/framework-queue-objects)

### Example

Example usage is shown below.

TBD - No sample code found

```cpp

```

## -see-also

[acxcircuit.h header](index.md)

