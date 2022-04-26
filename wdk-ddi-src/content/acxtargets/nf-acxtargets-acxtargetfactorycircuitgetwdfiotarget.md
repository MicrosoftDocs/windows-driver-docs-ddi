---
UID: NF:acxtargets.AcxTargetFactoryCircuitGetWdfIoTarget
tech.root: audio
title: AcxTargetFactoryCircuitGetWdfIoTarget
ms.date: 04/25/2022
targetos: Windows
description: The AcxTargetFactoryCircuitGetWdfIoTarget given an existing ACXTARGETFACTORYCIRCUIT object, returns a WDFIOTARGET object.
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
 - AcxTargetFactoryCircuitGetWdfIoTarget
f1_keywords:
 - AcxTargetFactoryCircuitGetWdfIoTarget
 - acxtargets/AcxTargetFactoryCircuitGetWdfIoTarget
dev_langs:
 - c++
---

## -description

The **AcxTargetFactoryCircuitGetWdfIoTarget** given an existing ACXTARGETFACTORYCIRCUIT object, returns a WDFIOTARGET object. For more information about WDF IO targets see [Initializing a General I/O Target](/windows-hardware/drivers/wdf/initializing-a-general-i-o-target).

## -parameters

### -param TargetFactoryCircuit

A pointer to a location of an existing ACXTARGETFACTORYCIRCUIT Object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

TBD - Code sample pending.

```cpp

TBD

```

## -see-also

- [acxtargets.h header](index.md)
 
TBD - Please review this topic  