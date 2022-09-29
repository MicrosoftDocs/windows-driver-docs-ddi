---
UID: NF:acxstreams.AcxStreamDispatchAcxRequest
tech.root: audio
title: AcxStreamDispatchAcxRequest
ms.date: 07/28/2022
targetos: Windows
description: The AcxStreamDispatchAcxRequest dispatches an ACX request using a WDFREQUEST framework request object.
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
 - AcxStreamDispatchAcxRequest
f1_keywords:
 - AcxStreamDispatchAcxRequest
 - acxstreams/AcxStreamDispatchAcxRequest
dev_langs:
 - c++
---

## -description

The **AcxStreamDispatchAcxRequest** dispatches an ACX request using a WDFREQUEST framework request object. AcxStreamDispatchAcxRequest is called within the context of an [EVT_ACX_OBJECT_PREPROCESS_REQUEST](../acxrequest/nc-acxrequest-evt_acx_object_preprocess_request.md) event handler registered through [AcxStreamInitAssignAcxRequestPreprocessCallback](nf-acxstreams-acxstreaminitassignacxrequestpreprocesscallback.md) to indicate the request should be handled by the ACX framework.

## -parameters

### -param Stream

An existing *ACXSTREAM* Object. An ACXSTREAM object represents an audio stream created by a circuit. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Request

The WDFREQUEST object handle that was passes to the *EVT_ACX_OBJECT_PREPROCESS_REQUEST* event handler. For general information about WDF requests, see [Creating Framework Request Objects](/windows-hardware/drivers/wdf/creating-framework-request-objects).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

For any call to the driver's EVT_ACX_OBJECT_PREPROCESS_REQUEST for an AcxStream object, the driver should either call WdfRequestComplete or AcxStreamDispatchAcxRequest, but not both.

### Example

Example usage is shown below.

```cpp
VOID
Codec_EvtStreamRequestPreprocess(
    _In_    ACXOBJECT  Object,
    _In_    ACXCONTEXT DriverContext,
    _In_    WDFREQUEST Request
    )
/*++

Routine Description:

    This function is an example of a preprocess routine.

--*/
{
    //
    // Just give the request back to ACX. Normally the driver would take steps to examine
    // the Request and take action if necessary.
    //
    AcxStreamDispatchAcxRequest((ACXSTREAM)Object, Request);
}
```

## -see-also

- [acxstreams.h header](index.md)
