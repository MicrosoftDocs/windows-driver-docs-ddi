---
UID: NF:acxcircuit.AcxFactoryCircuitInitAssignAcxRequestPreprocessCallback
tech.root: audio
title: AcxFactoryCircuitInitAssignAcxRequestPreprocessCallback
ms.date: 08/27/2021
targetos: Windows
description:  The AcxFactoryCircuitInitAssignAcxRequestPreprocessCallback function add a WDFREQUEST preprocess callback.
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
 - AcxFactoryCircuitInitAssignAcxRequestPreprocessCallback
f1_keywords:
 - AcxFactoryCircuitInitAssignAcxRequestPreprocessCallback
 - acxcircuit/AcxFactoryCircuitInitAssignAcxRequestPreprocessCallback
dev_langs:
 - c++
---

## -description

The AcxFactoryCircuitInitAssignAcxRequestPreprocessCallback function initializes defined AssignAcxRequest Preprocess callbacks for circuit factories.

## -parameters

### -param FactoryInit

An ACXFACTORYCIRCUIT_INIT structure that is used for circuit factory initialization. This is an opaque structure that is used to store ACX Circuit factory initialization information and associate the factory with a WDF device.
Use the [AcxFactoryCircuitInitAllocate function](nf-acxcircuit-acxfactorycircuitinitallocate.md) to initialize the ACXFACTORYCIRCUIT_INIT structure.

### -param EvtObjectAcxRequestPreprocess

A pointer to a [EVT_ACX_OBJECT_PREPROCESS_REQUEST](/windows-hardware/drivers/ddi/acxrequest/nc-acxrequest-evt_acx_object_preprocess_request.md) callback. 

### -param DriverContext

The driver context defined by the ACXCONTEXT object.  For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param RequestType

An [ACX_REQUEST_TYPE enum](/windows-hardware/drivers/ddi/acxrequest/ne-acxrequest-acx_request_type.md)  that defines different request types, such as AcxRequestTypeAny, AcxRequestTypeProperty, etc. 

### -param Set

Optional GUID to identify a specific item set ID.

### -param Id

An ID to indentify a specific item in the specified set ID.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

The driver can invoke this DDI multiple times to setup different preprocess callbacks. ACX invokes the first it finds that matches the specific incoming WDFREQUEST type.

### Example

Sample pending.

Example usage is shown below.

```cpp

```

## -see-also

- [acxcircuit.h header](index.md)

READY2GO
