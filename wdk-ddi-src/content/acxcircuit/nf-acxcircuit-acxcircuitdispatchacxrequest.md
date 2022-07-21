---
UID: NF:acxcircuit.AcxCircuitDispatchAcxRequest
tech.root: audio
title: AcxCircuitDispatchAcxRequest
ms.date: 06/16/2022
targetos: Windows
description: The AcxCircuitDispatchAcxRequest dispatches an ACX WDFREQUEST object to the ACX framework which will manage the request.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxcircuit.h
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
 - acxcircuit.h
api_name:
 - AcxCircuitDispatchAcxRequest
f1_keywords:
 - AcxCircuitDispatchAcxRequest
 - acxcircuit/AcxCircuitDispatchAcxRequest
dev_langs:
 - c++
---

## -description

The **AcxCircuitDispatchAcxRequest** dispatches an ACX WDFREQUEST object to the ACX framework which will manage the request. For more information about working with WDF request objects, see [Creating Framework Request Objects](/windows-hardware/drivers/wdf/creating-framework-request-objects) and [wdfrequest.h header](/windows-hardware/drivers/ddi/wdfrequest/).

## -parameters

### -param Circuit

An existing ACXCIRCUIT object. For more information, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Request

A standard WDFREQUEST object.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

```cpp
    //
    // Just give the request back to ACX.
    //
    status = AcxCircuitDispatchAcxRequest((ACXCIRCUIT)Object, Request);
```

## -see-also

- [acxcircuit.h header](index.md)

READY2GO

EDITCOMPLETE
