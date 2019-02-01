---
UID: NN:dbgmodel.IDataModelConcept
title: IDataModelConcept (dbgmodel.h)
description: Any object which represents a data model which is registered under a name or  is registered for a particular type signature must implement this concept and add it to the data model  object via IModelObject::SetConcept.
ms.assetid: f7e0a833-b878-454e-8741-816375c68110
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
-	IDataModelConcept
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelConcept interface

## -description

Any object which represents a data model which is registered under a name or  is registered for a particular type signature must implement this concept and add it to the data model  object via IModelObject::SetConcept.

Clients which create data models implement this interface.  It is most frequently consumed by the data model manager itself.


## -inheritance

IDataModelConcept interits from IUnknown. 

## -members

<p>IDataModelConcept has these methods.</p>
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
		<td>InitializeObject</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetName</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
