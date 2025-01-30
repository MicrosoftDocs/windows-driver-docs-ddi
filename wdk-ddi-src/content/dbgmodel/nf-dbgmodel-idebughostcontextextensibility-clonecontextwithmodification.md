---
UID: NF:dbgmodel.IDebugHostContextExtensibility.CloneContextWithModification
tech.root: debugger
title: IDebugHostContextExtensibility::CloneContextWithModification
ms.date: 01/15/2025
targetos: Windows
description: The CloneContextWithModification method clones the current host context, associates a particular extension blob with the cloned context, finalizes the context, and returns an immutable interface to the newly cloned context.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dbgmodel.h
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
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostContextExtensibility::CloneContextWithModification
f1_keywords:
 - IDebugHostContextExtensibility::CloneContextWithModification
 - dbgmodel/IDebugHostContextExtensibility::CloneContextWithModification
dev_langs:
 - c++
helpviewer_keywords:
 - CloneContextWithModification
---

## -description

This method clones the current host context, associates a particular extension blob with the cloned context, finalizes the context, and returns an immutable interface to the newly cloned context.

## -parameters

### -param blobId

This input parameter represents the id of the blob that will be associated with the cloned context.

### -param dataSize

This input parameter represents the size of the data to be associated with the cloned context.

### -param data

This input parameter is a pointer that points to the actual data to be associated with the cloned context.

### -param clonedContext

This parameter points to a IDebugHostContext pointer, which retrieves the cloned context. This is an Output parameter for the cloned context.

## -returns

If the method succeeds, it returns S_OK. If it fails, it returns an HRESULT error code.

## -remarks

## -see-also

[IDebugHostContextExtensibility interface](nn-dbgmodel-idebughostcontextextensibility.md)