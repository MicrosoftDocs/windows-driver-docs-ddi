---
UID: NF:dbgmodel.IDebugHostScriptHost.CreateContext
title: IDebugHostScriptHost::CreateContext (dbgmodel.h)
description: The CreateContext method is called by a script provider to create a new context in which to place the contents of the script.
ms.assetid: e7dbce17-bc44-4707-805e-2607263c8ce4
ms.date: 06/10/2019
keywords: ["IDebugHostScriptHost::CreateContext"]
f1_keywords:
 - "dbgmodel/IDebugHostScriptHost.CreateContext"
 - "IDebugHostScriptHost.CreateContext"
ms.keywords: IDebugHostScriptHost::CreateContext, CreateContext, IDebugHostScriptHost.CreateContext, IDebugHostScriptHost::CreateContext, IDebugHostScriptHost.CreateContext
req.header: dbgmodel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
- apiref
api_type: 
- COM
api_location: 
- dbgmodel.h
api_name: 
- IDebugHostScriptHost.CreateContext
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostScriptHost::CreateContext


## -description

The CreateContext method is called by a script provider to create a new context in which to place the contents of the script. Such context is represented by the [IDataModelScriptHostContext interface](nn-dbgmodel-idatamodelscripthostcontext.md). 

## -parameters

### -param script
The script for which to create a new context.

### -param scriptContext
The newly created script host context is returned here.

## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDataModelScriptHostContext interface](nn-dbgmodel-idatamodelscripthostcontext.md)

[IDebugHostScriptHost interface](nn-dbgmodel-idebughostscripthost.md)
