---
UID: NF:acxcircuit.AcxFactoryCircuitInitAssignAcxRequestPreprocessCallback
tech.root: audio
title: AcxFactoryCircuitInitAssignAcxRequestPreprocessCallback
ms.date: 08/17/2021
targetos: Windows
description:  The AcxFactoryCircuitInitAssignAcxRequestPreprocessCallback function initializes defined AssignAcxRequest Preprocess callbacks for circuit factories.
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

TBD - An ACXFACTORYCIRCUIT_INIT structure that is used for circuit factory initialization. This is an opaque structure that is used to store ACX Circuit factory initialization information and associate the factory with a WDF device.
Use the [AcxFactoryCircuitInitAllocate function](nf-acxcircuit-acxfactorycircuitinitallocate.md) to initialize the ACXFACTORYCIRCUIT_INIT structure.

### -param EvtObjectAcxRequestPreprocess

TDB - Not sure on this one - Is it a class making using of a PFN?

TBD - We were thinking that we didn't need to document most PFNs.

PFN_ACX_OBJECT_PREPROCESS_REQUEST EvtObjectAcxRequestPreprocess,


### -param DriverContext

The driver context defined by the ACXCONTEXT object.  (DocsTeam - need link to ACX Object Summary topic).

### -param RequestType

An [ACX_REQUEST_TYPE enum]()  that defines different request types, such as AcxRequestTypeAny  or AcxRequestTypeEvent. DOCS TEAM - Add link to enum in AcxRequest header.

### -param Set

Optional GUID to identify the associated (TBD - what type of?) Set.

### -param Id

TBD - An ID value that TBD  

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

TBD - No direct sample code was found.

Example usage is shown below.

```cpp

```

## -see-also

[acxcircuit.h header](index.md)

