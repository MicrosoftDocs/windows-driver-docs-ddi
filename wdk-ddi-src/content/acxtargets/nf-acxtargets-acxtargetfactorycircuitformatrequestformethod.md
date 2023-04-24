---
UID: NF:acxtargets.AcxTargetFactoryCircuitFormatRequestForMethod
tech.root: audio
title: AcxTargetFactoryCircuitFormatRequestForMethod
ms.date: 12/16/2022
targetos: Windows
description: The AcxTargetFactoryCircuitFormatRequestForMethod formats a WDFREQUEST as an ACX method request to be used on specified circuit factory target.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxtargets.h
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
 - HeaderDef
api_location:
 - acxtargets.h
api_name:
 - AcxTargetFactoryCircuitFormatRequestForMethod
f1_keywords:
 - AcxTargetFactoryCircuitFormatRequestForMethod
 - acxtargets/AcxTargetFactoryCircuitFormatRequestForMethod
dev_langs:
 - c++
---

## -description

The **AcxTargetFactoryCircuitFormatRequestForMethod**  formats a WDFREQUEST as an ACX method request to be used on specified circuit factory target.

## -parameters

### -param TargetFactoryCircuit

An ACXTARGETFACTORYCIRCUIT handle. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param Request

A WDFREQUEST handle described in [Summary of Framework Objects](/windows-hardware/drivers/wdf/summary-of-framework-objects). For general information about WDF requests, see [Creating Framework Request Objects](/windows-hardware/drivers/wdf/creating-framework-request-objects).

### -param Params

An initialized [ACX_REQUEST_PARAMETERS](/windows-hardware/drivers/ddi/acxrequest/ns-acxrequest-acx_request_parameters) structure that is used to store request parameter information.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxtargets.h header](index.md)
