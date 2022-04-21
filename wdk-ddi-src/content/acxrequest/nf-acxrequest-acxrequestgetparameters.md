---
UID: NF:acxrequest.AcxRequestGetParameters
tech.root: audio
title: AcxRequestGetParameters
ms.date: 02/08/2022
targetos: Windows
description: The AcxRequestGetParameters function gets ACX request parameters.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxrequest.h
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
 - LibDef
api_location:
 - acxrequest.h
api_name:
 - AcxRequestGetParameters
f1_keywords:
 - AcxRequestGetParameters
 - acxrequest/AcxRequestGetParameters
dev_langs:
 - c++
---

## -description

The **AcxRequestGetParameters** function gets ACX request parameters.

## -parameters

### -param Request

A standard WDFREQUEST object. 

For more information about working with WDF request objects, see [Creating Framework Request Objects](/windows-hardware/drivers/wdf/creating-framework-request-objects) and [wdfrequest.h header](/windows-hardware/drivers/ddi/wdfrequest/).

### -param Parameters

An [ACX_REQUEST_PARAMETERS](nf-acxrequest-acxrequestgetparameters.md) structure that describes the event items that can be used in an ACX request.

## -remarks

### Example

TBD

Example usage is shown below.

```cpp
    ACX_REQUEST_PARAMETERS      params;  
    WDFREQUEST                  request;

    ACX_REQUEST_PARAMETERS_INIT(&params);

    AcxRequestGetParameters(Request, &params);

    request = elementCtx->Request;
```

## -see-also

- [acxrequest.h header](index.md)

TBD - Please review this topic