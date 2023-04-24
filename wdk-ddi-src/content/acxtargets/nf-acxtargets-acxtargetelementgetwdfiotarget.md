---
UID: NF:acxtargets.AcxTargetElementGetWdfIoTarget
tech.root: audio
title: AcxTargetElementGetWdfIoTarget
ms.date: 12/16/2022
targetos: Windows
description: The AcxTargetElementGetWdfIoTarget given an existing ACXTARGETELEMENT object, returns its corresponding WDFIOTARGET object.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxtargets.h
req.idl: 
req.include-header: 
req.irql: <= DISPATCH_LEVEL
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
 - AcxTargetElementGetWdfIoTarget
f1_keywords:
 - AcxTargetElementGetWdfIoTarget
 - acxtargets/AcxTargetElementGetWdfIoTarget
dev_langs:
 - c++
---

## -description

The **AcxTargetElementGetWdfIoTarget** function given an existing ACXTARGETELEMENT object, returns its corresponding WDFIOTARGET object. For more information about WDF IO targets see [Initializing a General I/O Target](/windows-hardware/drivers/wdf/initializing-a-general-i-o-target).

## -parameters

### -param TargetElement

An existing ACXTARGETELEMENT Object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

The WDFIOTARGET object associated with the target element.

## -remarks

### Example

```cpp

    WDFIOTARGET ioTarget;

    ioTarget = AcxTargetElementGetWdfIoTarget(targetElement);

```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxtargets.h header](index.md)
