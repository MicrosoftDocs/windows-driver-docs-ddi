---
UID: NF:dbgmodel.IDebugHostContextExtensibility.CloneContextForModification
tech.root: debugger
title: IDebugHostContextExtensibility::CloneContextForModification
ms.date: 01/15/2025
targetos: Windows
description: The CloneContextForModification method clones a host context object and returns a one time modification interface to associate data with the context.
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
 - IDebugHostContextExtensibility::CloneContextForModification
f1_keywords:
 - IDebugHostContextExtensibility::CloneContextForModification
 - dbgmodel/IDebugHostContextExtensibility::CloneContextForModification
dev_langs:
 - c++
helpviewer_keywords:
 - CloneContextForModification
---

## -description

This method clones the current host context and returns a one-time modification interface to associate data with the context.

## -parameters

### -param extensionHandle

This parameter points to a IDebugHostContextExtension pointer, which is used to retrieve the host context extension. This is an Output parameter for the cloned context.

## -returns

If the method succeeds, it returns S_OK. If it fails, it returns an HRESULT error code.

## -remarks

The CloneContextForModification method is used to clone the current host context for one time modification and eventual immutability. It is necessary to call the [FinalizeContext method](nf-dbgmodel-idebughostcontextextension-finalizecontext.md) to finalize the cloned context and get back to the actual cloned context. After this, the returned host context becomes immutable and cannot be modified further.

## -see-also

[IDebugHostContextExtensibility interface](nn-dbgmodel-idebughostcontextextensibility.md)