---
UID: NN:dbgmodel.IDataModelScriptHostContext
title: IDataModelScriptHostContext (dbgmodel.h)
description: Implemented by the underlying host debugger, represents information about where the debug host is bridging the script.
ms.assetid: 89bc0f92-c13d-4516-b7b4-9105a2c2d479
ms.date: 10/05/2018
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
- IDataModelScriptHostContext
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptHostContext interface

## -description

Implemented by the underlying host debugger, represents information about where the debug host is bridging the script.


## -inheritance
IDataModelScriptHostContext interits from IUnknown. 
## -members

<p>IDataModelScriptHostContext has these methods.</p>
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
		<td>NotifyScriptChange</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetNamespaceObject</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

A host interface which is used by the script provider as a container for the contents of the script. How the contents of a script surface other than the manipulations that it performs to the object model of the debugger application is up to the particular debug host. This interface allows the script provider to get information about where to place its contents. See [Data Model C++ Scripting Interfaces](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-scripting) for more information.

The [IDebugHostScriptHost](nn-dbgmodel-idebughostscripthost.md) interface is the interface used by a script provider to get a context from the debug host for a newly created script. This context includes an object (provided by the debug host) where the script provider can place any bridges between the data model and the scripting environment. Such bridges might, for instance, be data model methods which invoke script functions. Doing this allows a caller on the data model side to invoke script methods by utilization of the Call method on [IModelMethod](nn-dbgmodel-imodelmethod.md) interface. 

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
