---
UID: NF:acxtargets.AcxTargetCircuitFormatRequestForProperty
tech.root: audio
title: AcxTargetCircuitFormatRequestForProperty
ms.date:  11/11/2021
targetos: Windows
description: The AcxTargetCircuitFormatRequestForMethod formats an ACX request using a WDFREQUEST framework request object.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxtargets.h
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
 - acxtargets.h
api_name:
 - AcxTargetCircuitFormatRequestForProperty
f1_keywords:
 - AcxTargetCircuitFormatRequestForProperty
 - acxtargets/AcxTargetCircuitFormatRequestForProperty
dev_langs:
 - c++
---

## -description

The **AcxTargetCircuitFormatRequestForMethod** formats an ACX request using a WDFREQUEST framework request object.

## -parameters

### -param TargetCircuit

A pointer to a location of an existing ACXTARGETCIRCUIT Object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Request

A pointer to a location that receives a handle to a WDFREQUEST framework request object described in [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects). For general information about WDF requests, see [Creating Framework Request Objects](/windows-hardware/drivers/wdf/creating-framework-request-objects).

### -param Params

An initialized [ACX_REQUEST_PARAMETERS](/windows-hardware/drivers/ddi/acxrequest/ns-acxrequest-acx_request_parameters.md) structure that is used to store request parameter information.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

Framework request objects represent I/O requests that the I/O manager has sent to a driver. Framework-based drivers process each I/O request by calling framework request object methods. For more information, see [Framework Request Objects](/windows-hardware/drivers/wdf/framework-request-objects).

### Example

```cpp
                    WDFREQUEST                  request = NULL;
                    WDF_REQUEST_SEND_OPTIONS    sendOptions;
                    WDF_OBJECT_ATTRIBUTES       attributes;
                    WDFIOTARGET                 ioTarget;

                    ACX_REQUEST_PARAMETERS             Params;

...
                    ioTarget = AcxTargetCircuitGetWdfIoTarget(circuit->AcxTargetCircuit);

                    WDF_OBJECT_ATTRIBUTES_INIT(&attributes);
                    attributes.ParentObject = CircuitCtx->AggregatorCircuit->Circuit;

                    status = WdfRequestCreate(&attributes, ioTarget, &request);    
                    if (!NT_SUCCESS(status)) 
                    {
                        AggregatorLogError(g_AggregatorLog, FLAG_INFO, "WdfRequestCreate for AudioModule command failed, %!STATUS!", status);
                        goto exit;
                    }

                    status = AcxTargetCircuitFormatRequestForProperty(circuit->AcxTargetCircuit, request, &Params);
```

## -see-also

- [acxtargets.h header](index.md)
 
TBD - Please review this topic