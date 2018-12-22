---
UID: NN:dbgmodel.IDataModelNameBinder
title: IDataModelNameBinder
description: Interface to a name binder – a component which can associate names in a context with objects or symbols.
ms.assetid: 9dbef43d-3f97-47f2-a5a6-5d273407dd6f
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
-	IDataModelNameBinder
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelNameBinder interface

## -description

Interface to a name binder – a component which can associate names in a context with objects or symbols.

The default name binder for script providers.

## -inheritance
IDataModelNameBinder interits from IUnknown. 
## -members

<p>IDataModelNameBinder has these methods.</p>
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
		<td>BindValue</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>BindReference</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>EnumerateValues</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>EnumerateReferences</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

The data model provides a standard way for script providers to determine the meaning of a given name in a given context (e.g.: determining what bar means for foo.bar) that will operate across a variety of script providers. This mechanism is known as a name binder and is represented by the IDataModelNameBinder interface. Such a binder encapsulates a set of rules about how the name resolves and how to deal with conflict resolution where a name is defined multiple times on an object. Part of these rules include things such as how a projected name (one added by a data model) resolves against a native name (one in the type system of the language being debugged). 

In order to provide a degree of consistency across script providers, the data model's script manager provides a default name binder'. This default name binder can be acquired via a call to the GetDefaultNameBinder method on the IDataModelScriptManager interface. 


## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
