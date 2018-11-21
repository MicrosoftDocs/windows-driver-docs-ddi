---
UID: NN:dbgmodel.IDebugHostModule2
title: IDebugHostModule2
author: windows-driver-content
description: An (IDebugHostSymbol derived) interface to a particular module.
ms.assetid: d0afd86c-b48e-46ce-8eeb-248705d7e467
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
-	IDebugHostModule2
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostModule2 interface

## -description

An (IDebugHostSymbol derived) interface to a particular module.


## -inheritance
IDebugHostModule2 interits from IDebugHostModule. 
## -members

<p>IDebugHostModule2 has these methods.</p>
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
		<td>GetImageName</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetBaseLocation</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetVersion</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>FindTypeByName</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>FindSymbolByRVA</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>FindSymbolByName</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>FindContainingSymbolByRVA</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

The debugger's notion of a module that is loaded within some address space is represented in two distinct ways in the data model: 

- At the type system level via the IDebugHostModule interface. Here, a module is a symbol and core attributes of the module are interface method calls

- Projected at the data model level via the Debugger.Models.Module data model. This is an extensible encapsulation of the type system IDebugHostModule representation of a module.

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
