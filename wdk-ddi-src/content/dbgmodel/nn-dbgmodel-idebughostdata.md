---
UID: NN:dbgmodel.IDebugHostData
title: IDebugHostData
description: An (IDebugHostSymbol derived) interface to data.
ms.assetid: d5d3a8dd-885d-46c5-89ab-e3dc6b221654
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
-	IDebugHostData
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostData interface

## -description

An (IDebugHostSymbol derived) interface to data.

Represents data within a module (were this within a structure or class it would be an IDebugHostField).


## -inheritance
IDebugHostData interits from IDebugHostSymbol. 
## -members

<p>IDebugHostData has these methods.</p>
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
		<td>GetContext</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>EnumerateChildren</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetSymbolKind</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetName</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetType</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetContainingModule</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetLocationKind</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetLocation</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetValue</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

Data in modules which is not a member of another type is represented by the IDebugHostData interface. 

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
