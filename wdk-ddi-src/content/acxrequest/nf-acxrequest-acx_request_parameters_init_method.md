---
UID: NF:acxrequest.ACX_REQUEST_PARAMETERS_INIT_METHOD
tech.root: audio
title: ACX_REQUEST_PARAMETERS_INIT_METHOD
ms.date: 09/29/2022
targetos: Windows
description: The ACX_REQUEST_PARAMETERS_INIT_METHOD initializes an ACX_REQUEST_PARAMETERS struct with ACX method parameters.
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

The **ACX_REQUEST_PARAMETERS_INIT_METHOD** function initializes an ACX_REQUEST_PARAMETERS struct with ACX method parameters.

## -parameters

### -param Params

A pointer to [ACX_REQUEST_PARAMETERS](ns-acxrequest-acx_request_parameters.md) structure that is used to store method parameters.

### -param Set

A method Set ID (GUID).

### -param Id

A method ID (ULONG) within the method Set ID. 

### -param Verb

The ACX method verb to send as defined by the [ACX_METHOD_VERB](ne-acxrequest-acx_method_verb.md) enumeration.

### -param ItemType

The [ACX_ITEM_TYPE](ne-acxrequest-acx_item_type.md) type of item being sent, for example AcxItemTypeCircuit.

### -param ItemId

The item ID of the ItemType, for example the pin ID if the ItemType is a pin.

### -param Args

An optional Args buffer holding additional parameters for the specified method. Set to null if not present.

### -param ArgsCb

The count in bytes (size) of the Args buffer. Set to 0 if Args field is not used.

### -param Result

An optional Result buffer to old the result of the operation. Set to null if not present or if *SendMethod needs to allocate it when ResultCb is not zero. Caller is responsible for freeing the allocated buffer.

### -param ResultCb

The count in bytes (size) of the Result buffer. Set to 0 if Result is not used.

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

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxrequest.h header](index.md)


