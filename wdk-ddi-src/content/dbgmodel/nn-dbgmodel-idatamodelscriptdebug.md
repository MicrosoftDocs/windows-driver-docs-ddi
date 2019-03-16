---
UID: NN:dbgmodel.IDataModelScriptDebug
title: IDataModelScriptDebug (dbgmodel.h)
description: The core interface that a script provider must provide in order to make a script debuggable. 
ms.assetid: 11133d81-6a1e-4e83-8e85-63c282f4eb16
ms.date: 10/04/2018
ms.topic: interface
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
- apiref
api_type: 
- COM
api_location: 
- dbgmodel.h
api_name: 
- IDataModelScriptDebug
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptDebug interface

## -description

The core interface that a script provider must provide in order to make a script debuggable. The implementation class of the IDataModelScript interface must QueryInterface for IDataModelScriptDebug if the script is debuggable.

Any script which is debuggable indicates this capability via the presence of the IDataModelScriptDebug interface on the same component which implements IDataModelScript. The query for this interface by the debug host or the debugger application hosting the data model is what indicates the presence of the debug capability. 

## -inheritance
IDataModelScriptDebug interits from IUnknown. 
## -members

<p>IDataModelScriptDebug has these methods.</p>
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
		<td>GetDebugState</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetCurrentPosition</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetStack</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>SetBreakpoint</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>FindBreakpointById</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>EnumerateBreakpoints</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetEventFilter</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>SetEventFilter</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>StartDebugging</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>StopDebugging</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

The infrastructure for script providers in the data model also provides a concept around debugging scripts. Any script that wishes to expose debugging capabilities to the debug host and the debugger application hosting the data model can do so by having debuggable scripts implement the IDataModelScriptDebug interface in addition to the IDataModelScript interface. The presence of this interface on the script indicates to the infrastructure that it is debuggable. 

While the IDataModelScriptDebug interface is the starting point to get access to the debug capabilities of a script provider, it is joined by a set of other interfaces in providing overall debug capabilities.

IDataModelScriptDebug

IDataModelScriptDebugClient

IDataModelScriptDebugStack

IDataModelScriptDebugStackFrame

IDataModelScriptDebugVariableSetEnumerator

IDataModelScriptDebugBreakpoint

IDataModelScriptDebugBreakpointEnumerator


## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
