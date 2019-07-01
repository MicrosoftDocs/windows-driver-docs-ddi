---
UID: NN:dbgmodel.IDataModelManager2
title: IDataModelManager2 (dbgmodel.h)
description: The second version of the interface for the data model manager.  This is the interface by which new objects are created, intrinsic values are boxed and unboxed, and models are registered for types. 
ms.assetid: 3cdf03e0-7682-4b98-906c-b4fcacc844a4
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
- IDataModelManager2
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelManager2 interface

## -description

The second version of the interface for the data model manager.  This is the interface by which new objects are created, intrinsic values are boxed and unboxed, and models are registered for types. 

This interface is never directly implemented by a client.

This version 2 of the interface supports all of the previous methods with identical signatures and includes additional new methods that provide added functionality. The new methods are listed in the header at the end of the section for that interface.

## -inheritance
IDataModelManager2 interits from [IDataModelManager](nn-dbgmodel-idatamodelmanager.md). 
## -members

<p>IDataModelManager2 has these methods.</p>
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
		<td>Close</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>CreateNoValue</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>CreateErrorObject</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>CreateTypedObject</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>CreateTypedObjectReference</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>CreateSyntheticObject</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>CreateDataModelObject</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>CreateIntrinsicObject</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>CreateTypedIntrinsicObject</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetModelForTypeSignature</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetModelForType</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>RegisterModelForTypeSignature</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>UnregisterModelForTypeSignature</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>RegisterExtensionForTypeSignature</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>UnregisterExtensionForTypeSignature</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>CreateMetadataStore</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetRootNamespace</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>RegisterNamedModel</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>UnregisterNamedModel</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>AcquireNamedModel</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>AcquireSubNamespace</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>CreateTypedIntrinsicObjectEx</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
