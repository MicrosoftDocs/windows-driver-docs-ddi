---
UID: NF:acxtargets.AcxTargetStreamGetTargetElement
tech.root: audio
title: AcxTargetStreamGetTargetElement
ms.date: 04/26/2022
targetos: Windows
description: The AcxTargetStreamGetTargetElement function, given a valid element index value, will return an ACXTARGETELEMENT ACX object that is associated with the specified circuit.
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
 - AcxTargetStreamGetTargetElement
f1_keywords:
 - AcxTargetStreamGetTargetElement
 - acxtargets/AcxTargetStreamGetTargetElement
dev_langs:
 - c++
---

## -description

The **AcxTargetStreamGetTargetElement** function, given a valid element index value, will return an ACXTARGETELEMENT ACX object that is associated with the specified circuit.

## -parameters

### -param TargetStream

A pointer to the location of an existing ACXTARGETSTREAM object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param ElementIndex

The numeric index value for the specified element.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

Sample Pending

### Example

```cpp

```

## -see-also

- [acxtargets.h header](index.md)

TBD - Please review this topic