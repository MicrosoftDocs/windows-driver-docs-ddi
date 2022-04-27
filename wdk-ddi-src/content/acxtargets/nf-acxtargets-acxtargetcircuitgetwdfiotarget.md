---
UID: NF:acxtargets.AcxTargetCircuitGetWdfIoTarget
tech.root: audio
title: AcxTargetCircuitGetWdfIoTarget
ms.date: 02/03/2022
targetos: Windows
description: The AcxTargetCircuitGetWdfIoTarget function will return an WDFIOTARGET  object that is associated with the specified circuit. 
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
 - AcxTargetCircuitGetWdfIoTarget
f1_keywords:
 - AcxTargetCircuitGetWdfIoTarget
 - acxtargets/AcxTargetCircuitGetWdfIoTarget
dev_langs:
 - c++
---

## -description

The **AcxTargetCircuitGetWdfIoTarget** function will return an WDFIOTARGET WDF object that is associated with the specified circuit. 

## -parameters

### -param TargetCircuit

A pointer to a location of an existing ACXTARGETCIRCUIT Object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

Returns a  WDFIOTARGET Object that is associated with the specified circuit.

## -remarks

Framework request objects represent I/O requests that the I/O manager has sent to a driver. Framework-based drivers process each I/O request by calling framework request object methods. For more information, see [Framework Request Objects](/windows-hardware/drivers/wdf/framework-request-objects).

### Example
 
This example code shows the use of AcxTargetCircuitGetWdfIoTarget. 

```cpp
                // Within an aggregated device,
                // the module class id + instance id must uniquely identify a module. 
                // There should never be duplicates.
                if (IsEqualGUIDAligned(descriptor->ClassId, moduleProperty->ClassId) &&
                    descriptor->InstanceId == moduleProperty->InstanceId)
                {
                    WDFREQUEST                  request = NULL;
                    WDF_REQUEST_SEND_OPTIONS    sendOptions;
                    WDF_OBJECT_ATTRIBUTES       attributes;
                    WDFIOTARGET                 ioTarget;

                    // We've now identified which aggregated device this call is targeting.
                    // The cached module information contains the ID adjusted with the aggregation device
                    // index. remove the aggregation device index before forwarding the call to the aggregated circuit.
                    moduleProperty->InstanceId = AUDIOMODULE_GET_INSTANCEID(moduleProperty->InstanceId);

                    ioTarget = AcxTargetCircuitGetWdfIoTarget(circuit->AcxTargetCircuit);
```

## -see-also

- [acxtargets.h header](index.md)
 
TBD - Please review this topic