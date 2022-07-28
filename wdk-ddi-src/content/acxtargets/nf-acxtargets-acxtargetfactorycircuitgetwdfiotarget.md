---
UID: NF:acxtargets.AcxTargetFactoryCircuitGetWdfIoTarget
tech.root: audio
title: AcxTargetFactoryCircuitGetWdfIoTarget
ms.date: 07/22/2022
targetos: Windows
description: The AcxTargetFactoryCircuitGetWdfIoTarget given an existing ACXTARGETFACTORYCIRCUIT object, returns its corresponding WDFIOTARGET object.
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

The **AcxTargetFactoryCircuitGetWdfIoTarget** function given an existing ACXTARGETFACTORYCIRCUIT object, returns its corresponding WDFIOTARGET object. For more information about WDF IO targets see [Initializing a General I/O Target](/windows-hardware/drivers/wdf/initializing-a-general-i-o-target).

## -parameters

### -param TargetFactoryCircuit

An existing ACXTARGETFACTORYCIRCUIT Object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

Returns the WDFIOTARGET object associated with the ACXTARGETFACTORYCIRCUIT.

## -remarks

### Example

```cpp

```

## -see-also

- [acxtargets.h header](index.md)
 
 