---
UID: NF:acxrequest.ACX_REQUEST_PARAMETERS_INIT
tech.root: audio
title: ACX_REQUEST_PARAMETERS_INIT
ms.date: 02/08/2022
targetos: Windows
description: The ACX_REQUEST_PARAMETERS_INIT_METHOD function initializes ACX request methods.
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
 - ACX_REQUEST_PARAMETERS_INIT
f1_keywords:
 - ACX_REQUEST_PARAMETERS_INIT
 - acxrequest/ACX_REQUEST_PARAMETERS_INIT
dev_langs:
 - c++
---

## -description

The **ACX_REQUEST_PARAMETERS_INIT_METHOD** function initializes ACX request methods.

## -parameters

### -param Parameters

An [ACX_REQUEST_PARAMETERS](nf-acxrequest-acxrequestgetparameters.md) structure that describes the event items that can be used in an ACX request.
 
## -remarks

### Example

Example usage is shown below.

```cpp
            arg     = circuitArg;
            result  = 0;

            //
            // Format and send the request. 
            //
            ACX_REQUEST_PARAMETERS_INIT_METHOD(
                &params,
                methodsTests[i].MethodSet,
                methodsTests[i].MethodId,
                AcxMethodVerbSend,
                AcxItemTypeCircuit,
                AcxItemIdNone,
                &arg, sizeof(arg),      // Args & size
                &result, sizeof(result) // Result & size
                );
```

## -see-also

[acxrequest.h header](index.md)

