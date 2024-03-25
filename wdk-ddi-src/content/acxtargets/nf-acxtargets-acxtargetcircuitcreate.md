---
UID: NF:acxtargets.AcxTargetCircuitCreate
tech.root: audio
title: AcxTargetCircuitCreate
ms.date: 12/16/2022
targetos: Windows
description: The AcxTargetCircuitCreate function is used to create an ACX target circuit.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxtargets.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
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
 - AcxTargetCircuitCreate
f1_keywords:
 - AcxTargetCircuitCreate
 - acxtargets/AcxTargetCircuitCreate
dev_langs:
 - c++
---

## -description

The **AcxTargetCircuitCreate** function is used to create an ACX target circuit.

## -parameters

### -param Device

A WDFDEVICE object (described in [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects)) that is associated with the specified ACXCIRCUIT.

### -param Attributes

Additional Attributes defined using a [WDF_OBJECT_ATTRIBUTES](/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes) structure that are used to set various object's values: cleanup and destroy callbacks, context type, and to specify its parent object.

### -param Config

An initialized [ACX_TARGET_CIRCUIT_CONFIG structure](ns-acxtargets-acx_target_circuit_config.md) that describes the configuration of the target circuit.

### -param TargetCircuit

A pointer to a location that receives a handle to the new ACXTARGETCIRCUIT Object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

```cpp
    ACX_TARGET_CIRCUIT_CONFIG targetCfg;
    ACX_TARGET_CIRCUIT_CONFIG_INIT(&targetCfg);
    targetCfg.SymbolicLinkName = link;

    WDF_OBJECT_ATTRIBUTES_INIT(&attributes);
    attributes.ParentObject = Circuit;

    RETURN_NTSTATUS_IF_FAILED(AcxTargetCircuitCreate(AcxCircuitGetWdfDevice(Circuit), &attributes, &targetCfg, TargetCircuit));
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxtargets.h header](index.md)
