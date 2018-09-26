---
UID: NF:dbgmodel.IDebugHostScriptHost.CreateContext
title: IDebugHostScriptHost::CreateContext
author: windows-driver-content
description: TBD
ms.assetid: e7dbce17-bc44-4707-805e-2607263c8ce4
ms.author: windowsdriverdev
ms.date: 09/20/2018  
ms.topic: method
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
-	apiref
api_type: 
-	COM
api_location: 
-	dbgmodel.h
api_name: 
-	IDebugHostScriptHost.CreateContext
product: Windows
targetos: Windows


tech.root: debugger
---

# IDebugHostScriptHost::CreateContext


## -description

The CreateContext method is called by a script provider to create a new context in which to place the contents of the script. Such context is represented by the IDataModelScriptHostContext interface. 

## -parameters

### -param script

### -param scriptContext
The newly created script host context is returned here.

## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDebugHostScriptHost interface](nn-dbgmodel-idebughostscripthost.md)
