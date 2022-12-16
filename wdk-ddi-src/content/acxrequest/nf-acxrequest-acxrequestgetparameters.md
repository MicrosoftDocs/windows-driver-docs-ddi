---
UID: NF:acxrequest.AcxRequestGetParameters
tech.root: audio
title: AcxRequestGetParameters
ms.date: 11/10/2022
targetos: Windows
description: The AcxRequestGetParameters function gets ACX request parameters from a WDFREQUEST.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxrequest.h
req.idl: 
req.include-header: 
req.irql: DISPATCH_LEVEL
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

The **AcxRequestGetParameters** function gets ACX request parameters from a WDFREQUEST.

## -parameters

### -param Request

An I/O WDFREQUEST object. 

For more information about working with WDF request objects, see [Creating Framework Request Objects](/windows-hardware/drivers/wdf/creating-framework-request-objects) and [wdfrequest.h header](/windows-hardware/drivers/ddi/wdfrequest/).

### -param Parameters

An [ACX_REQUEST_PARAMETERS](nf-acxrequest-acxrequestgetparameters.md) structure that is initialized with the WDFREQUEST.

## -remarks

### Example

Example usage is shown below.

```cpp
    ACX_REQUEST_PARAMETERS      params;  
    WDFREQUEST                  request;

    ACX_REQUEST_PARAMETERS_INIT(&params);

    AcxRequestGetParameters(Request, &params);

    request = elementCtx->Request;
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxrequest.h header](index.md)
