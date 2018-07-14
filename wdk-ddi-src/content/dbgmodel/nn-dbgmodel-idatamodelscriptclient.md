---
UID: NN:dbgmodel.IDataModelScriptClient
title: IDataModelScriptClient
author: windows-driver-content
description: TBD
ms.assetid: 2eb01e40-ef25-4593-bc4f-bf689ec73a6b
ms.author: windowsdriverdev
ms.date:  07/13/2018
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
-	IDataModelScriptClient
product: Windows
targetos: Windows
---

# IDataModelScriptClient interface

## -description

Interface a component directly using debugger script must implement as a multi-way communication channel with the script.


## -inheritance
IDataModelScriptClient interits from IUnknown. 
## -members

<p>IDataModelScriptClient has these methods.</p>
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
		<td>ReportError</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

A client interface which is used by the script provider in order to communicate information to a user interface. Script providers do not implement this interface. The application hosting the data model which wishes to make use of script providers does. A script provider will call into methods of the script client to report status, errors, etc...

## -see-also

[Debugger Data Model C++ Overview](https://review.docs.microsoft.com/en-us/windows-hardware/drivers/debugger/data-model-cpp-overview?branch=debugger-op-ref-docs)
