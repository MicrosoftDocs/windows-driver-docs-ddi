---
UID: NF:acxtargets.AcxTargetFactoryCircuitCreate
tech.root: audio
title: AcxTargetFactoryCircuitCreate
ms.date: 04/26/2022
targetos: Windows
description: The AcxTargetFactoryCircuitCreate function returns an handle to a new ACXTARGETFACTORYCIRCUIT ACX object. 
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxtargets.h
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
 - acxtargets.h
api_name:
 - AcxTargetFactoryCircuitCreate
f1_keywords:
 - AcxTargetFactoryCircuitCreate
 - acxtargets/AcxTargetFactoryCircuitCreate
dev_langs:
 - c++
---

## -description

The **AcxTargetFactoryCircuitCreate** function returns an handle to a new ACXTARGETFACTORYCIRCUIT ACX object. 

## -parameters

### -param Device

A WDFDEVICE object (described in [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that is associated with the specified ACXCIRCUIT. 

### -param Attributes

Additional Attributes defined using a [WDF_OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes) structure that are used to set various object’s values: cleanup and destroy callbacks, context type, and to specify its parent object.

### -param Config

An initialized [ACX_TARGET_FACTORY_CIRCUIT_CONFIG structure](ns-acxtargets-acx_target_factory_circuit_config.md) that describes the configuration of the target factory circuit.

### -param TargetFactoryCircuit

A pointer to a location that receives a handle to the new ACXTARGETFACTORYCIRCUIT Object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

```cpp

```

## -see-also

- [acxtargets.h header](index.md)
 
READY2GO
