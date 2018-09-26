---
UID: NN:dbgmodel.IModelIterator
title: IModelIterator
author: windows-driver-content
description: TBD
ms.assetid: 29497013-68f8-4e35-9402-e13faf9e9483
ms.author: windowsdriverdev
ms.date: 07/16/2018
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
-	IModelIterator
product: Windows
targetos: Windows
tech.root: debugger
---

# IModelIterator interface

## -description

An iterator of contained objects (client implemented and returned by IIterableConcept).


## -inheritance
IModelIterator interits from IUnknown. 
## -members

<p>IModelIterator has these methods.</p>
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
		<td>Reset</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetNext</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

**Iterable Concept**

An object which is a container of other objects and wishes to express the ability to iterate over those contained objects can support the iterable concept by an implementation of the IIterableConcept and IModelIterator interfaces. There is a very important relationship between support of the iterable concept and support of the indexable concept. An object which supports random access to the contained objects can support the indexable concept in addition to the iterable concept. In this case, the iterated elements must also produce a default index which, when passed to the indexable concept refer to the same object. A failure to satisfy this invariant will result in undefined behavior in the debug host. 

## -see-also
