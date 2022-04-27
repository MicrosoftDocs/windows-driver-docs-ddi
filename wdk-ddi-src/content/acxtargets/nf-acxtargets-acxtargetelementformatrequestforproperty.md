---
UID: NF:acxtargets.AcxTargetElementFormatRequestForProperty
tech.root: audio
title: AcxTargetElementFormatRequestForProperty
ms.date: 04/25/2022
targetos: Windows
description: The AcxTargetElementFormatRequestForProperty dispatches an ACX request using a WDFREQUEST framework request object.
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
 - AcxTargetElementFormatRequestForProperty
f1_keywords:
 - AcxTargetElementFormatRequestForProperty
 - acxtargets/AcxTargetElementFormatRequestForProperty
dev_langs:
 - c++
---

## -description

The **AcxTargetElementFormatRequestForProperty** function dispatches an ACX request using a WDFREQUEST framework request object.

## -parameters

### -param TargetElement

An existing ACXTARGETELEMENT Object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Request

A pointer to a location that receives a handle to a WDFREQUEST framework request object described in [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects). For general information about WDF requests, see [Creating Framework Request Objects](/windows-hardware/drivers/wdf/creating-framework-request-objects).

### -param Params

An initialized [ACX_REQUEST_PARAMETERS](/windows-hardware/drivers/ddi/acxrequest/ns-acxrequest-acx_request_parameters.md) structure that is used to store request parameter information.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

```cpp
    WDFIOTARGET                 ioTarget;
    WDF_OBJECT_ATTRIBUTES       attributes;
    WDFREQUEST                  request = NULL;

        ioTarget = AcxTargetElementGetWdfIoTarget(elementCtx->TargetElements[i]->TargetElement);

        WDF_OBJECT_ATTRIBUTES_INIT(&attributes);
        attributes.ParentObject = elementCtx->TargetElements[i]->TargetElement;

        status = AcxTargetElementFormatRequestForProperty(elementCtx->TargetElements[i]->TargetElement, request, &targetParams[i]);
```

## -see-also

- [acxtargets.h header](index.md)
 
TBD - Please review this topic
 
 