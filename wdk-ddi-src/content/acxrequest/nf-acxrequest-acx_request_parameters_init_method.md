---
UID: NF:acxrequest.ACX_REQUEST_PARAMETERS_INIT_METHOD
tech.root: audio
title: ACX_REQUEST_PARAMETERS_INIT_METHOD
ms.date: 02/07/2022
targetos: Windows
description: The ACX_REQUEST_PARAMETERS_INIT_METHOD initializes ACX request methods.
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
 - ACX_REQUEST_PARAMETERS_INIT_METHOD
f1_keywords:
 - ACX_REQUEST_PARAMETERS_INIT_METHOD
 - acxrequest/ACX_REQUEST_PARAMETERS_INIT_METHOD
dev_langs:
 - c++
---

## -description

The **ACX_REQUEST_PARAMETERS_INIT_METHOD** function initializes ACX request methods.

## -parameters

### -param Params

An initialized [ACX_REQUEST_PARAMETERS](ns-acxrequest-acx_request_parameters.md) structure that is used to store circuit information.

### -param Set

A set of Methods that are TBD.

### -param Id

The Method ID that will be TBD.

### -param Verb

The Acx Method Verb to send.

### -param ItemType

The [ACX_ITEM_TYPE](/windows-hardware/drivers/ddi/acxrequest/ne-acxrequest-acx_item_type.md) type of item being sent, for example AcxItemTypeCircuit.

### -param ItemId

TDB - An Item Id, for example for a pin number in a circuit.

### -param Args

Arguments provided to the initialization process.

### -param ArgsCb

The count in bytes (size) of the Args.

### -param Result

The result of the TBD.

### -param ResultCb

The count in bytes (size) of the Result.

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

