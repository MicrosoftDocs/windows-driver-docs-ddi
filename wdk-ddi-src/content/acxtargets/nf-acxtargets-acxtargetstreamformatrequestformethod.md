---
UID: NF:acxtargets.AcxTargetStreamFormatRequestForMethod
tech.root: audio
title: AcxTargetStreamFormatRequestForMethod
ms.date: 04/26/2022
targetos: Windows
description: The AcxTargetStreamFormatRequestForMethod formats a WDFREQUEST as an ACX method request to be used on specified stream target.
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
 - AcxTargetStreamFormatRequestForMethod
f1_keywords:
 - AcxTargetStreamFormatRequestForMethod
 - acxtargets/AcxTargetStreamFormatRequestForMethod
dev_langs:
 - c++
---

## -description

The **AcxTargetStreamFormatRequestForMethod** formats a WDFREQUEST as an ACX method request to be used on specified stream target.

## -parameters

### -param TargetStream

An existing ACXTARGETSTREAM object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Request

A WDFREQUEST handle described in [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects). For general information about WDF requests, see [Creating Framework Request Objects](/windows-hardware/drivers/wdf/creating-framework-request-objects).

### -param Params

An initialized [ACX_REQUEST_PARAMETERS](/windows-hardware/drivers/ddi/acxrequest/ns-acxrequest-acx_request_parameters.md) structure that is used to store method request parameter information.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

A WDFREQUEST is a driver created I/O requests. Framework-based drivers process each I/O request by calling framework request object methods. For more information, see [Framework Request Objects](/windows-hardware/drivers/wdf/framework-request-objects).

### Example

```cpp

```

## -see-also

- [acxtargets.h header](index.md)

READY2GO
