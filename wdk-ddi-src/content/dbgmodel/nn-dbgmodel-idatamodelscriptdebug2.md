---
UID: NN:dbgmodel.IDataModelScriptDebug2
title: IDataModelScriptDebug2
author: windows-driver-content
description: TBD
ms.assetid: 29d61401-a385-4f5e-bda3-81ee79f5c5f8
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
-	IDataModelScriptDebug2
product: Windows
targetos: Windows
---

# IDataModelScriptDebug2 interface

## -description

 An optional interface on scripts (objects which implement IDataModelScript).  If this interface is supported, the script provider has a debug engine capable of some limited form of 'script debugging'.  This may include stepping, setting breakpoints, inspecting data, etc...


## -inheritance
IDataModelScriptDebug2 interits from IDataModelScriptDebug. 
## -members

<p>IDataModelScriptDebug2 has these methods.</p>
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
	<tr>
		<td>SetBreakpointAtFunction</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

The infrastructure for script providers in the data model also provides a concept around debugging scripts. Any script that wishes to expose debugging capabilities to the debug host and the debugger application hosting the data model can do so by having debuggable scripts implement the IDataModelScriptDebug interface in addition to the IDataModelScript interface. The presence of this interface on the script indicates to the infrastructure that it is debuggable. 

## -see-also

[Debugger Data Model C++ Overview](https://review.docs.microsoft.com/en-us/windows-hardware/drivers/debugger/data-model-cpp-overview?branch=debugger-op-ref-docs)
