---
UID: NN:dbgmodel.IModelKeyReference2
title: IModelKeyReference2
author: windows-driver-content
description: TBD
ms.assetid: 7edde32e-56bf-4a15-b0e3-114449026a97
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
-	IModelKeyReference2
product: Windows
targetos: Windows
tech.root: debugger
---

# IModelKeyReference2 interface

## -description

A reference to a key on a data model object.


## -inheritance
IModelKeyReference2 interits from IModelKeyReference. 
## -members

<p>IModelKeyReference2 has these methods.</p>
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
		<td>GetKeyName</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetOriginalObject</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetContextObject</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetKey</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetKeyValue</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>SetKey</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>SetKeyValue</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>OverrideContextObject</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

**Key References** 

A key reference is, in essence, a handle to a key on a particular object. A client can retrieve such handle via methods such as GetKeyReference and use the handle later to get or set the value of the key without necessarily holding onto the original object. This type of object is an implementation of the IModelKeyReference or IModelKeyReference2 interface which is boxed into an IModelObject. The model object will return a kind of ObjectKeyReference when queried and then intrinsic value is a VT_UNKNOWN which is guaranteed to be queryable for IModelKeyReference. In process, it is guaranteed to be statically castable to IModelKeyReference. 

## -see-also

[Debugger Data Model C++ Overview](https://review.docs.microsoft.com/en-us/windows-hardware/drivers/debugger/data-model-cpp-overview?branch=debugger-op-ref-docs)
