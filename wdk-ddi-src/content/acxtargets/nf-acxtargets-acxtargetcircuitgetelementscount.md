---
UID: NF:acxtargets.AcxTargetCircuitGetElementsCount
tech.root: audio
title: AcxTargetCircuitGetElementsCount
ms.date: 04/22/2022
targetos: Windows
description: The AcxTargetCircuitGetElementsCount function given an ACXTARGETCIRCUIT object, returns an elements count.
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
 - AcxTargetCircuitGetElementsCount
f1_keywords:
 - AcxTargetCircuitGetElementsCount
 - acxtargets/AcxTargetCircuitGetElementsCount
dev_langs:
 - c++
---

## -description

The **AcxTargetCircuitGetElementsCount** function given an ACXTARGETCIRCUIT object, returns an elements count.

## -parameters

### -param TargetCircuit

A pointer to a location of an existing ACXTARGETCIRCUIT Object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

Framework request objects represent I/O requests that the I/O manager has sent to a driver. Framework-based drivers process each I/O request by calling framework request object methods. For more information, see [Framework Request Objects](/windows-hardware/drivers/wdf/framework-request-objects).

### Example

```cpp
    ULONG                       elementCount;

    elementCount = AcxTargetCircuitGetElementsCount(audioCircuit->AcxTargetCircuit);
```

## -see-also

- [acxtargets.h header](index.md)

TBD - Please review this topic