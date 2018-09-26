---
UID: NN:dbgmodel.IDataModelScriptTemplateEnumerator
title: IDataModelScriptTemplateEnumerator
author: windows-driver-content
description: TBD
ms.assetid: 7d5f9983-35d8-4983-94af-3419f843b838
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
-	IDataModelScriptTemplateEnumerator
product: Windows
targetos: Windows
tech.root: debugger
---

# IDataModelScriptTemplateEnumerator interface

## -description

An enumerator which enumerates an available set of script templates.

An enumerator interface that the script provider implements in order to advertise all the various templates it supports.


## -inheritance
IDataModelScriptTemplateEnumerator interits from IUnknown. 
## -members

<p>IDataModelScriptTemplateEnumerator has these methods.</p>
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

A script provider can provide one or more templates which pre-fill content into newly created scripts in some user interface. If any of these templates are provided, the script provider must implement an enumerator over them which is returned upon a call to the EnumerateTemplates method. 
## -see-also

[Debugger Data Model C++ Overview](https://review.docs.microsoft.com/en-us/windows-hardware/drivers/debugger/data-model-cpp-overview?branch=debugger-op-ref-docs)
