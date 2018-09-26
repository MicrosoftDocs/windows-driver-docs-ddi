---
UID: NN:dbgmodel.IDataModelScriptDebugClient
title: IDataModelScriptDebugClient
author: windows-driver-content
description: TBD
ms.assetid: e6dbd395-a973-4447-a423-9d26ce13c90b
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
-	IDataModelScriptDebugClient
product: Windows
targetos: Windows
tech.root: debugger
---

# IDataModelScriptDebugClient interface

## -description

The client of the script debugger implements this interface as a part of a two-way communication channel with the script debugger.

The user interface which wishes to provide the capability of script debugging implements the IDataModelScriptDebugClient interface. The script provider utilizes this interface to pass debug information back and forth (e.g.: events which occur, breakpoints, etc...)


## -inheritance
IDataModelScriptDebugClient interits from IUnknown. 
## -members

<p>IDataModelScriptDebugClient has these methods.</p>
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
		<td>NotifyDebugEvent</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

The debug host or debugger application which wishes to provide an interface around script debugging must provide an implementation of the IDataModelScriptDebugClient interface to the script debugger via the StartDebugging method on the debug interface for the script. 

The IDataModelScriptDebugClient is the communication channel across which debug events are passed and control goes from the script execution engine to a debugger interface. 


## -see-also

[Debugger Data Model C++ Overview](https://review.docs.microsoft.com/en-us/windows-hardware/drivers/debugger/data-model-cpp-overview?branch=debugger-op-ref-docs)
