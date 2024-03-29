---
UID: NF:dbgmodel.IDataModelScriptDebug2.GetStack
title: IDataModelScriptDebug2::GetStack (dbgmodel.h)
description: "The IDataModelScriptDebug2::GetStack method gets the current call stack at the break position in a script debugger session."
ms.date: 08/21/2018
keywords: ["IDataModelScriptDebug2::GetStack"]
ms.keywords: IDataModelScriptDebug2::GetStack, GetStack, IDataModelScriptDebug2.GetStack, IDataModelScriptDebug2::GetStack, IDataModelScriptDebug2.GetStack
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
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - IDataModelScriptDebug2::GetStack
 - dbgmodel/IDataModelScriptDebug2::GetStack
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelScriptDebug2::GetStack
---

# IDataModelScriptDebug2::GetStack


## -description

The GetStack method gets the current call stack at the break position. This method may only be called when the script is broken into the debugger.

## -parameters

### -param stack

A component implementing [IDataModelScriptDebugStack](nn-dbgmodel-idatamodelscriptdebugstack.md) is returned here representing the call stack state at the position of the break.

## -returns

This method returns HRESULT that indicates success or failure.

## -see-also

[IDataModelScriptDebug2 interface](nn-dbgmodel-idatamodelscriptdebug2.md)

