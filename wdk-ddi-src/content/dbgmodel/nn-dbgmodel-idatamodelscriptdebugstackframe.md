---
UID: NN:dbgmodel.IDataModelScriptDebugStackFrame
title: IDataModelScriptDebugStackFrame
author: windows-driver-content
description: TBD
ms.assetid: c0701fe1-41b8-4f51-91e8-74506b344b08
ms.author: windowsdriverdev
ms.date: 07/13/2018
ms.topic: interface
ms.prod: windows-hardware
ms.technology: windows-devices
req.header: dbgmodel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.umdf-ver:
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
-	IDataModelScriptDebugStackFrame
product: Windows
targetos: Windows
---

# IDataModelScriptDebugStackFrame interface

## -description

An interface to a stack frame in the script.

The script provider implements this interface to expose the notion of a particular stack frame within the call stack.


## -inheritance
IDataModelScriptDebugStackFrame interits from IUnknown. 
## -members

<p>IDataModelScriptDebugStackFrame has these methods.</p>
<table>
	<tr>
		<td>Method</td>
		<td>Description</td>
	</tr>
	<tr>
		<td>QueryInterface</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>AddRef</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>Release</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetName</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetPosition</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>IsTransitionPoint</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetTransition</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>Evaluate</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>EnumerateLocals</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>EnumerateArguments</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

A particular frame of the call stack when broken into the script debugger can be retrieved via a call to the GetStackFrame method on the IDataModelScriptDebugStack interface representing the stack segment where the break occurred. The IDataModelScriptDebugStackFrame interface which is returned to represent this frame. 

## -see-also

[Debugger Data Model C++ Overview](https://review.docs.microsoft.com/en-us/windows-hardware/drivers/debugger/data-model-cpp-overview?branch=debugger-op-ref-docs)
