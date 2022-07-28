---
UID: NF:acxcircuit.AcxFactoryCircuitInitAssignProperties
tech.root: audio
title: AcxFactoryCircuitInitAssignProperties
ms.date: 07/28/2022
targetos: Windows
description: The AcxFactoryCircuitInitAssignProperties function assigns one or more ACX properties for the ACXFACTORYCIRCUIT.
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
 - HeaderDef
api_location:
 - acxcircuit.h
api_name:
 - AcxFactoryCircuitInitAssignProperties
f1_keywords:
 - AcxFactoryCircuitInitAssignProperties
 - acxcircuit/AcxFactoryCircuitInitAssignProperties
dev_langs:
 - c++
---

## -description

The AcxFactoryCircuitInitAssignProperties function assigns one or more ACX properties for the ACXFACTORYCIRCUIT.

## -parameters

### -param FactoryInit

An ACXFACTORYCIRCUIT_INIT structure that is used for circuit factory initialization. This is an opaque structure that is used to store ACX Circuit factory initialization information and associate the factory with a WDF device.

Use the [AcxFactoryCircuitInitAllocate function](nf-acxcircuit-acxfactorycircuitinitallocate.md) to initialize the ACXFACTORYCIRCUIT_INIT structure.

### -param Properties

An [ACX_PROPERTY_ITEM structure](/windows-hardware/drivers/ddi/acxrequest/acxrequest/ns-acxrequest-acx_property_item) that defines a set of properties that will be used for circuit initialization. 

### -param PropertiesCount

A count of the properties that will be used for the circuit factory initialization. This is a one based count.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

Drivers should only add driver owned properties.

### Example
 
Sample pending.

Example usage is shown below.

```cpp

```

## -see-also

- [acxcircuit.h header](index.md)

