---
UID: NN:dbgmodel.IDebugHostType
title: IDebugHostType (dbgmodel.h)
description: An (IDebugHostSymbol derived) interface to a particular type.
ms.assetid: f4fb5043-a364-45f6-9d87-43850ac0f140
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
- apiref
api_type: 
- COM
api_location: 
- dbgmodel.h
api_name: 
- IDebugHostType
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostType interface

## -description

An ([IDebugHostSymbol](nn-dbgmodel-idebughostsymbol.md) derived) interface to a particular type.

A given language/native type is described by the [IDebugHostType2](nn-dbgmodel-idebughosttype2.md) or IDebugHostType interfaces. Note that some of the methods on these interfaces only apply for specific kinds of types.


## -inheritance
IDebugHostType interits from [IDebugHostSymbol](nn-dbgmodel-idebughostsymbol.md). 
## -members

<p>IDebugHostType has these methods.</p>
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
		<td>GetTypeKind</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetSize</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetBaseType</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetHashCode</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetIntrinsicType</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetBitField</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetPointerKind</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetMemberType</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>CreatePointerTo</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetArrayDimensionality</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetArrayDimensions</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>CreateArrayOf</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetFunctionCallingConvention</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetFunctionReturnType</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetFunctionParameterTypeCount</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetFunctionParameterTypeAt</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>IsGeneric</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetGenericArgumentCount</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetGenericArgumentAt</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
