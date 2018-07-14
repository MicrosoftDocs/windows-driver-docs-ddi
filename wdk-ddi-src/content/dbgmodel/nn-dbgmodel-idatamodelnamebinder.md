---
UID: NN:dbgmodel.IDataModelNameBinder
title: IDataModelNameBinder
author: windows-driver-content
description: TBD
ms.assetid: 9dbef43d-3f97-47f2-a5a6-5d273407dd6f
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
-	IDataModelNameBinder
product: Windows
targetos: Windows
---

# IDataModelNameBinder interface

## -description

Interface to a name binder – a component which can associate names in a context with objects or symbols.

The default name binder for script providers.

## -inheritance
IDataModelNameBinder interits from IUnknown. 
## -members

<p>IDataModelNameBinder has these methods.</p>
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
		<td>BindValue</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>BindReference</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>EnumerateValues</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>EnumerateReferences</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

## -see-also

[Debugger Data Model C++ Overview](https://review.docs.microsoft.com/en-us/windows-hardware/drivers/debugger/data-model-cpp-overview?branch=debugger-op-ref-docs)