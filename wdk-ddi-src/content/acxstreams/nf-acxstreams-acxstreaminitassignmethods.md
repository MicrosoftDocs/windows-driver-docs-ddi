---
UID: NF:acxstreams.AcxStreamInitAssignMethods
tech.root: audio
title: AcxStreamInitAssignMethods
ms.date: 07/28/2022
targetos: Windows
description: The AcxStreamInitAssignMethods function assigns an array of methods to a stream using the ACXSTREAM_INIT object.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxstreams.h
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
 - acxstreams.h
api_name:
 - AcxStreamInitAssignMethods
f1_keywords:
 - AcxStreamInitAssignMethods
 - acxstreams/AcxStreamInitAssignMethods
dev_langs:
 - c++
---

## -description

The **AcxStreamInitAssignMethods** function assigns an array of methods to a stream using the *ACXSTREAM_INIT* object.

## -parameters

### -param StreamInit

Defined by a ACXSTREAM_INIT object, that is used to define the stream initialization. For more information about ACX Objects, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Methods

An array of ACX_METHOD_ITEM that describes the methods to be assigned.

### -param MethodsCount

A one based count of the number of methods in the Methods array.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
    static ACX_METHOD_ITEM StreamMethods[] =
    {
        {
            &KSMETHODSETID_AcxTestMethod,
            KSMETHOD_ACXSTREAM_TEST_IN2OUT,
            ACX_METHOD_ITEM_FLAG_SEND,
            Codec_EvtTestIn2OutMethodCallback,
            NULL,               // Reserved
            sizeof(ULONG),      // ControlCb
            sizeof(ULONG),      // ValueCb
        },
    };

    static ULONG StreamMethodsCount = SIZEOF_ARRAY(StreamMethods);

    status = AcxStreamInitAssignMethods(StreamInit,
                                         StreamMethods,
                                         StreamMethodsCount);
```

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxstreams.h header](index.md)
