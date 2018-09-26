---
UID: NN:dbgmodel.IDebugHostScriptHost
title: IDebugHostScriptHost
author: windows-driver-content
description: TBD
ms.assetid: d0376d3b-d770-44e6-8b8f-5d8cc361bf14
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
-	IDebugHostScriptHost
product: Windows
targetos: Windows
tech.root: debugger
---

# IDebugHostScriptHost interface

## -description

An interface which the underlying debugger host must implement in order to manage data model scripts.

The interface which indicates the capability of the debug host to take part in the scripting environment. This interface allows for the creation of contexts which inform scripting engines of where to place objects.


## -inheritance
IDebugHostScriptHost inherits from IUnknown. 
## -members

<p>IDebugHostScriptHost has these methods.</p>
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
		<td>CreateContext</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

The IDebugHostScriptHost interface is the interface used by a script provider to get a context from the debug host for a newly created script. This context includes an object (provided by the debug host) where the script provider can place any bridges between the data model and the scripting environment. Such bridges might, for instance, be data model methods which invoke script functions. Doing this allows a caller on the data model side to invoke script methods by utilization of the Call method on IModelMethod interface. 

## -see-also

[Debugger Data Model C++ Overview](https://review.docs.microsoft.com/en-us/windows-hardware/drivers/debugger/data-model-cpp-overview?branch=debugger-op-ref-docs)
