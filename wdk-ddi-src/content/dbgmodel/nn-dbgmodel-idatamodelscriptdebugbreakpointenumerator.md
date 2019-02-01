---
UID: NN:dbgmodel.IDataModelScriptDebugBreakpointEnumerator
title: IDataModelScriptDebugBreakpointEnumerator (dbgmodel.h)
description: An enumerator of breakpoints within the script.
ms.assetid: 98079ec9-c73a-4d88-8016-8fb53c461d91
ms.date: 07/13/2018
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
-	apiref
api_type: 
-	COM
api_location: 
-	dbgmodel.h
api_name: 
-	IDataModelScriptDebugBreakpointEnumerator
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptDebugBreakpointEnumerator interface

## -description

An enumerator of breakpoints within the script.

The script provider implements this to enumerate all of the breakpoints which currently exist within the script (whether enabled or not).


## -inheritance
IDataModelScriptDebugBreakpointEnumerator interits from IUnknown. 
## -members

<p>IDataModelScriptDebugBreakpointEnumerator has these methods.</p>
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
		<td>Reset</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetNext</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

If a script provider supports debugging, it must also keep track of all breakpoints associated with each and every script and be capable of enumerating those breakpoints to the debug interface. The enumerator for breakpoints is acquired via the EnumerateBreakpoints method on the debug interface for a given script.

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
