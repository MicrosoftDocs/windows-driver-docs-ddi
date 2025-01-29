---
UID: NF:dbgmodel.IDebugHostContextExtension.FinalizeContext
tech.root: debugger
title: IDebugHostContextExtension::FinalizeContext
ms.date: 01/15/2025
targetos: Windows
description: The FinalizeContext method finalizes modifications of the host context, makes it immutable, and returns an interface to the context.
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
 - IDebugHostContextExtension::FinalizeContext
f1_keywords:
 - IDebugHostContextExtension::FinalizeContext
 - dbgmodel/IDebugHostContextExtension::FinalizeContext
dev_langs:
 - c++
helpviewer_keywords:
 - FinalizeContext
---

## -description

## -parameters

The FinalizeContext method finalizes modifications of the host context, makes it immutable, and returns an interface to the context.

### -param immutableContext

A pointer to a pointer variable that receives the IDebugHostContext interface to the immutable context.

## -returns

If the method succeeds, it returns S_OK. Otherwise, it returns an HRESULT error code.

## -remarks

## -see-also

[IDebugHostContextExtension interface](nn-dbgmodel-idebughostcontextextension.md)