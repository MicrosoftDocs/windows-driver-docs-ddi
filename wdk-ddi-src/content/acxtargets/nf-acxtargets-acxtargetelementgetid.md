---
UID: NF:acxtargets.AcxTargetElementGetId
tech.root: audio
title: AcxTargetElementGetId
ms.date: 12/16/2022
targetos: Windows
description: The AcxTargetElementGetId given an existing ACXTARGETELEMENT object, returns its corresponding ID value.
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
 - AcxTargetElementGetId
f1_keywords:
 - AcxTargetElementGetId
 - acxtargets/AcxTargetElementGetId
dev_langs:
 - c++
---

## -description

The **AcxTargetElementGetId** function given an existing ACXTARGETELEMENT object, returns its corresponding ID value.

## -parameters

### -param TargetElement

An existing ACXTARGETELEMENT Object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -returns

The ID value associated with the element.

## -remarks

### Example

```cpp
    ACXTARGETELEMENT targetElement = nullptr;

    targetElement = circuitCtx->TargetVolumeHandler;

    ACX_REQUEST_PARAMETERS_INIT_PROPERTY(&targetParams,
                                         propertySet,
                                         propertyId,
                                         params.Parameters.Property.Verb,
                                         params.Parameters.Property.ItemType,
                                         AcxTargetElementGetId(targetElement),
                                         params.Parameters.Property.Control,
                                         params.Parameters.Property.ControlCb,
                                         params.Parameters.Property.Value,
                                         params.Parameters.Property.ValueCb);

```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxtargets.h header](index.md)
