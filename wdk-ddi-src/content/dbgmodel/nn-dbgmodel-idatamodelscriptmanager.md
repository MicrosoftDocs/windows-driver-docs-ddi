---
UID: NN:dbgmodel.IDataModelScriptManager
title: IDataModelScriptManager
author: windows-driver-content
description: The core interface to the script management capabilities of the data model manager.  Queried from the data model manager.
ms.assetid: 456082be-779f-4504-a068-4c625759cc54
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
-	IDataModelScriptManager
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelScriptManager interface

## -description

The core interface to the script management capabilities of the data model manager.  Queried from the data model manager.


## -inheritance
IDataModelScriptManager interits from IUnknown. 
## -members

<p>IDataModelScriptManager has these methods.</p>
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
		<td>GetDefaultNameBinder</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>RegisterScriptProvider</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>UnregisterScriptProvider</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>FindProviderForScriptType</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>FindProviderForScriptExtension</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>EnumerateScriptProviders</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

In addition to the Data Model Manager's role as the central authority on object creation and extensibility, it is also responsible for the management of an abstract concept of scripts. From the perspective of the Script Manager portion of the Data Model Manager, a script is something which can be dynamically loaded, unloaded, and potentially debugged by a provider in order to extend or provide new functionality to the data model. 
A script provider is a component which bridges a language (e.g.: NatVis, JavaScript, etc...) to the data model. It registers one or more file extensions (e.g.: ".NatVis", ".js") which are handled by the provider allowing a debugger client or a user interface to allow for loading of script files with that particular extension by delegation to the provider. 

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
