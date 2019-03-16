---
UID: NN:dbgmodel.IIndexableConcept
title: IIndexableConcept (dbgmodel.h)
description: Any object which is a container that supports random access retrieval of elements from given N-dimensional indexers implements IIndexableConcept.
ms.assetid: 8d92fead-7ccb-40f5-9eb7-b7d6ef5cec45
ms.date: 10/04/2018
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
- IIndexableConcept
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IIndexableConcept interface

## -description

Any object which is a container that supports random access retrieval of elements from given N-dimensional indexers implements this concept.

It is legal for an object to be indexable (via support of IIndexableConcept) and not iterable (via lack of support for  IIterableConcept).


## -inheritance
IIndexableConcept interits from IUnknown. 
## -members

<p>IIndexableConcept has these methods.</p>
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
		<td>GetDimensionality</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetAt</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>SetAt</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

## -see-also
