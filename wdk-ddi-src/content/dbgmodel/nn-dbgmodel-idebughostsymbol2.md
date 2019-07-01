---
UID: NN:dbgmodel.IDebugHostSymbol2
title: IDebugHostSymbol2 (dbgmodel.h)
description: An interface to a particular symbol.
ms.assetid: 669f0a11-dfd4-4877-a054-bde97ead4387
ms.date: 06/11/2019
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
- IDebugHostSymbol2
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostSymbol2 interface

## -description

An interface to a particular symbol.

This version 2 of the interface supports all of the previous methods with identical signatures and includes additional new methods that provide added functionality. The new methods are listed in the header at the end of the section for that interface.

## -inheritance
IDebugHostSymbol2 interits from [IDebugHostSymbol](nn-dbgmodel-idebughostsymbol.md). 
## -members

<p>IDebugHostSymbol2 has these methods.</p>
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
		<td>CompareAgainst</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>EnumerateChildrenEx</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetLanguage</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

Every symbol that can be returned from the data model host will derive in some fashion from [IDebugHostSymbol](nn-dbgmodel-idebughostsymbol.md). This is the core interface that every symbol implements regardless of the kind of symbol. Depending on the kind of symbol, a given symbol may implement a set of other interfaces which return attributes more unique to the particular kind of symbol represented by this interface.

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
