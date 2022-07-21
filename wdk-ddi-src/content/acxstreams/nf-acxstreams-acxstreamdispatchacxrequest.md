---
UID: NF:acxstreams.AcxStreamDispatchAcxRequest
tech.root: audio
title: AcxStreamDispatchAcxRequest
ms.date: 07/12/2021
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

The AcxStreamDispatchAcxRequest dispatches an ACX request using a WDFREQUEST framework request object.

## -parameters

### -param Stream

A pointer to a location that receives a handle to the new ACXSTREAM Object.

An ACXSTREAM object represents an audio stream created by a circuit. The stream is composed of a list of elements created based on the parent circuit’s elements. For more information, see [ACX - Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Request

A pointer to a location that receives a handle to a WDFREQUEST framework request object described in [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects). For general information about WDF requests, see [Creating Framework Request Objects](/windows-hardware/drivers/wdf/creating-framework-request-objects).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
 status = AcxStreamDispatchAcxRequest((ACXSTREAM)Object, Request);
```



## -see-also

- [acxstreams.h header](index.md)

TBD - Please review this topic