---
UID: NN:dbgmodel.IDataModelScriptProvider
title: IDataModelScriptProvider
author: windows-driver-content
description: Any script provider implementing a bridge between a dynamic language and the data model must implement this interface to represent the provider.
ms.assetid: efec4d86-2d7b-4c57-adec-3ecff8c3ce7d
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
-	IDataModelScriptProvider
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptProvider interface

## -description

Any script provider implementing a bridge between a dynamic language and the data model must implement this interface to represent the provider.

## -inheritance
IDataModelScriptProvider interits from IUnknown. 
## -members

<p>IDataModelScriptProvider has these methods.</p>
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
		<td>GetName</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetExtension</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>CreateScript</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetDefaultTemplateContent</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>EnumerateTemplates</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

Any extension which wants to be a script provider must provide an implementation of the IDataModelScriptProvider interface and register such with the script manager portion of the data model manager via the RegisterScriptProvider method. 

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
