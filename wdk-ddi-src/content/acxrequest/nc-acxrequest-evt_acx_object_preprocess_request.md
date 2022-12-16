---
UID: NC:acxrequest.EVT_ACX_OBJECT_PREPROCESS_REQUEST
tech.root: audio
title: EVT_ACX_OBJECT_PREPROCESS_REQUEST
ms.date: 11/10/2022
targetos: Windows
description: The EVT_ACX_OBJECT_PREPROCESS_REQUEST callback is used by the driver to preprocess I/O WDFREQUESTs. 
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxrequest.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
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
 - EVT_ACX_OBJECT_PREPROCESS_REQUEST
f1_keywords:
 - EVT_ACX_OBJECT_PREPROCESS_REQUEST
 - acxrequest/EVT_ACX_OBJECT_PREPROCESS_REQUEST
dev_langs:
 - c++
---

## -description

The **EVT_ACX_OBJECT_PREPROCESS_REQUEST** callback is used by the driver to preprocess I/O WDFREQUESTs. 

## -parameters

### -param Object

An ACX object associated with the request. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param DriverContext

The driver context defined by the ACXCONTEXT object.  

### -param Request

An WDFREQUEST object. 

For more information about working with WDF request objects, see [Creating Framework Request Objects](/windows-hardware/drivers/wdf/creating-framework-request-objects) and [wdfrequest.h header](/windows-hardware/drivers/ddi/wdfrequest/).

## -remarks

### Example

Example usage is shown below.

```cpp
EVT_ACX_OBJECT_PREPROCESS_REQUEST   CodecR_EvtCircuitRequestPreprocess;

...

VOID
CodecR_EvtCircuitRequestPreprocess(
    _In_    ACXOBJECT  Object,
    _In_    ACXCONTEXT DriverContext,
    _In_    WDFREQUEST Request
    )
/*++

Routine Description:

    This function is an example of a preprocess routine.

--*/
{
    PAGED_CODE();

    UNREFERENCED_PARAMETER(DriverContext);
    
    ASSERT(Object != NULL);
    ASSERT(DriverContext);
    ASSERT(Request);

    // Add the handling of the request here.
    // Driver is responsable for completing the request when done.

    //
    // Else, just give the request back to ACX.
    //
    (VOID)AcxCircuitDispatchAcxRequest((ACXCIRCUIT)Object, Request);
}
```


### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxrequest.h header](index.md)
