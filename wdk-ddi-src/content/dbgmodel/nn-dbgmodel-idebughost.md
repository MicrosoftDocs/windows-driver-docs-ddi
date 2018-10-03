---
UID: NN:dbgmodel.IDebugHost
title: IDebugHost
author: windows-driver-content
description: The core interface to the underlying debugger.
ms.assetid: 1eb195cc-10aa-4820-9e1b-a892f8d08e39
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
-	IDebugHost
product: Windows
targetos: Windows
tech.root: debugger
---

# IDebugHost interface

## -description

The core interface to the underlying debugger.


## -inheritance
IDebugHost interits from IUnknown. 
## -members

<p>IDebugHost has these methods.</p>
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
		<td>GetHostDefinedInterface</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetCurrentContext</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetDefaultMetadata</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

The IDebugHost interface is the core interface of any data model host. 

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
