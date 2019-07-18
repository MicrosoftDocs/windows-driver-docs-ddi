---
UID: NN:dbgmodel.IDebugHostMemory2
title: IDebugHostMemory2 (dbgmodel.h)
description: The memory access interface to the underlying debugger.
ms.assetid: f34471dc-175b-46e3-aeec-18841184e940
ms.date: 06/11/2019
ms.topic: interface
f1_keywords:
 - "dbgmodel/IDebugHostMemory2"
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
- IDebugHostMemory2
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostMemory2 interface

## -description

The memory access interface to the underlying debugger.

This version 2 of the interface supports all of the previous methods with identical signatures and includes additional new methods that provide added functionality. The new methods are listed in the header at the end of the section for that interface.

## -inheritance
IDebugHostMemory2 interits from [IDebugHostMemory](nn-dbgmodel-idebughostmemory.md). 
## -members

<p>IDebugHostMemory2 has these methods.</p>
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
		<td>ReadBytes</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>WriteBytes</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>ReadPointers</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>WritePointers</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetDisplayStringForLocation</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>LinearizeLocation</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
