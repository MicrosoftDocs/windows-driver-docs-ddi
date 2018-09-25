---
UID: NN:dbgmodel.IModelPropertyAccessor
title: IModelPropertyAccessor
author: windows-driver-content
description: TBD
ms.assetid: 719a97dc-26eb-4b5a-9f68-50c4a9069bae
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
-	IModelPropertyAccessor
product: Windows
targetos: Windows
tech.root: debugger
---

# IModelPropertyAccessor interface

## -description

The data model representation of a  property accessor (get/set).


## -inheritance
IModelPropertyAccessor interits from IUnknown. 
## -members

<p>IModelPropertyAccessor has these methods.</p>
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
		<td>GetValue</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>SetValue</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

A property accessor in the data model is an implementation of the IModelPropertyAccessor interface which is boxed into an IModelObject. The model object will return a kind of ObjectPropertyAccessor when queried and the intrinsic value is a VT_UNKNOWN which is guaranteed to be queryable for IModelPropertyAccessor. In process, it is guaranteed to be statically castable to IModelPropertyAccessor. 

A property accessor is an indirect way to get a method call for getting and setting a key value in the data model. If a given key's value is a property accessor, the GetKeyValue and SetKeyValue methods will automatically notice this and call the property accessor's underlying GetValue or SetValue methods as appropriate. 


## -see-also

[Debugger Data Model C++ Overview](https://review.docs.microsoft.com/en-us/windows-hardware/drivers/debugger/data-model-cpp-overview?branch=debugger-op-ref-docs)
