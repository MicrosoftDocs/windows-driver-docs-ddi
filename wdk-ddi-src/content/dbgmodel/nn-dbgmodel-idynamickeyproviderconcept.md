---
UID: NN:dbgmodel.IDynamicKeyProviderConcept
title: IDynamicKeyProviderConcept
author: windows-driver-content
description: If a client wants to take over the storage of keys and values for an object, it can implement this concept interface.
ms.assetid: f7a64209-5764-4a95-b099-0a0a04599ea4
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
-	IDynamicKeyProviderConcept
product: Windows
targetos: Windows
tech.root: debugger
---

# IDynamicKeyProviderConcept interface

## -description

If a client wants to take over the storage of keys and values for an object, it can implement this concept interface.

The object is a dynamic provider of keys and wishes to take over all key queries from the core data model. This interface is typically used as a bridge to dynamic languages such as JavaScript.

## -inheritance
IDynamicKeyProviderConcept interits from IUnknown. 
## -members

<p>IDynamicKeyProviderConcept has these methods.</p>
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
		<td>GetKey</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>SetKey</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>EnumerateKeys</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

**Dynamic Provider Concepts**

While the data model itself normally handles key and concept management for objects, there are times where that notion is less than ideal. In particular, when a client wishes to create a bridge between the data model and something else which is truly dynamic (e.g.: JavaScript), it can be valuable to take over key and concept management from the implementation in the data model. As the core data model is the one and only implementation of IModelObject, this is instead done via a combination of two concepts: the dynamic key provider concept and the dynamic concept provider concept. While it would be typical to implement both or neither, there is no requirement for such. 

If both are implemented, the dynamic key provider concept must be added before the dynamic concept provider concept. 
Both of these concepts are special. They effectively flip a switch on the object changing it from "statically managed" to "dynamically managed". These concepts can only be set if there are no keys/concepts managed by the data model on the object. Once these concepts are added to an object, the action of doing this is irrevocable. 
There is an additional semantic difference around extensibility between an IModelObject which is a dynamic concept provider and one that is not. These concepts are intended to allow clients to create bridges between the data model and dynamic language systems such as JavaScript. The data model has a concept of extensibility that differs somewhat fundamentally from systems like JavaScript in that there is a tree of parent models rather than a linear chain like the JavaScript prototype chain. To allow a better relationship to such systems, an IModelObject which is a dynamic concept provider has a single data model parent. That single data model parent is a normal IModelObject which can have an arbitrary number of parent models as is typical for the data model. Any requests to the dynamic concept provider to add or remove parents are automatically redirected to the single parent. From an outsider's perspective, it looks as though the dynamic concept provider has a normal tree style chain of parent models. The implementer of the dynamic concept provider concept is the only object (outside of the core data model) that is aware of the intermediate single parent. That single parent can be linked against the dynamic language system to provide a bridge (e.g.: placed into the JavaScript prototype chain). 


## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
