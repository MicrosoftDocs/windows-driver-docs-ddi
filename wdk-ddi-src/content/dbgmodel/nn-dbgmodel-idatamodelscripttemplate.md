---
UID: NN:dbgmodel.IDataModelScriptTemplate
title: IDataModelScriptTemplate
author: windows-driver-content
description: TBD
ms.assetid: 1b0e8279-e0bf-4a27-8d48-69072054b7f8
ms.author: windowsdriverdev
ms.date: 07/13/2018
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
-	IDataModelScriptTemplate
product: Windows
targetos: Windows
tech.root: debugger
---

# IDataModelScriptTemplate interface

## -description

Any script provider wanting to have pre-filled template content implements this interface per template.

Script providers can provide one or more templates which serve as starting points for users to author scripts. A debugger application which provides a built-in editor can prefill new scripts with template content as advertised by the provider through this interface.


## -inheritance
IDataModelScriptTemplate interits from IUnknown. 
## -members

<p>IDataModelScriptTemplate has these methods.</p>
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
		<td>GetDescription</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetContent</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

Script providers that want to present pre-filled content for new scripts (e.g.: to aid users writing scripts in a debugger user interface) can do so by providing one or more script templates. Such templates are components which implement the IDataModelScriptTemplate interface and are returned via either the GetDefaultTemplate method or EnumerateTemplates method on the script provider. 

## -see-also

[Debugger Data Model C++ Overview](https://review.docs.microsoft.com/en-us/windows-hardware/drivers/debugger/data-model-cpp-overview?branch=debugger-op-ref-docs)
