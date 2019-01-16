---
UID: NN:dbgmodel.IDebugHostPublic
title: IDebugHostPublic
description: An (IDebugHostSymbol derived) interface to a public symbol (address/name only).
ms.assetid: 18775b1d-4efc-422c-8920-21de383fb5b9
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
-	IDebugHostPublic
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostPublic interface

## -description

An (IDebugHostSymbol derived) interface to a public symbol (address/name only).

Represents a symbol within the publics table of a PDB. This does not have type information associated with it. It is a name and address.


## -inheritance
IDebugHostPublic interits from IDebugHostSymbol. 
## -members

<p>IDebugHostPublic has these methods.</p>
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
</table>

## -remarks

Public symbols represent things in the public table within a symbol file. They are, in effect, export addresses. There is no type information associated with a public symbol -- only an address. Unless a public symbol is explicitly requested by the caller, the debug host prefers to return private symbols for every inquiry. A public symbol is expressed by the IDebugHostPublic interface.

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
