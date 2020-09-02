---
UID: NF:dbgmodel.IDataModelScriptDebugVariableSetEnumerator.GetNext
title: IDataModelScriptDebugVariableSetEnumerator::GetNext (dbgmodel.h)
description: The GetNext method moves the enumerator to the next variable in the set and returns the variable's name, value, and any metadata associated with it.
ms.assetid: 3e5b85ef-4766-42e5-a300-14f5271f1c2d
ms.date: 09/10/2018
keywords: ["IDataModelScriptDebugVariableSetEnumerator::GetNext"]
ms.keywords: IDataModelScriptDebugVariableSetEnumerator::GetNext, GetNext, IDataModelScriptDebugVariableSetEnumerator.GetNext, IDataModelScriptDebugVariableSetEnumerator::GetNext, IDataModelScriptDebugVariableSetEnumerator.GetNext
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
 - IDataModelScriptDebugVariableSetEnumerator::GetNext
 - dbgmodel/IDataModelScriptDebugVariableSetEnumerator::GetNext
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDataModelScriptDebugVariableSetEnumerator.GetNext
---

# IDataModelScriptDebugVariableSetEnumerator::GetNext


## -description

The GetNext method moves the enumerator to the next variable in the set and returns the variable's name, value, and any metadata associated with it. If the enumerator has hit the end of the set, the error E_BOUNDS is returned. Once the E_BOUNDS marker has been returned from the GetNext method, it will continue to produce E_BOUNDS when called again unless an intervening Reset call is made.

## -parameters

### -param variableName

The name of the variable in the set is returned here as a string allocated by the SysAllocString function. The caller is responsible for freeing the returned string via SysFreeString.

### -param variableValue

The current value of the variable is returned here. The value must be marshaled out to an [IModelObject](nn-dbgmodel-imodelobject.md) representation. Every property or other construct on the [IModelObject](nn-dbgmodel-imodelobject.md) must be able to be acquired while the debugger is in a break state.

### -param variableMetadata

Optional metadata about the variable and its presentation may be returned here.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDataModelScriptDebugVariableSetEnumerator interface](nn-dbgmodel-idatamodelscriptdebugvariablesetenumerator.md)

