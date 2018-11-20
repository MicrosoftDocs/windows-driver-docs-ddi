---
UID: NN:dbgmodel.IDebugHostEvaluator
title: IDebugHostEvaluator
author: windows-driver-content
description: The expression evaluator interface to the underlying debugger.
ms.assetid: c8723b55-2e4b-4b4d-8910-c21ad40c6076
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
-	IDebugHostEvaluator
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostEvaluator interface

## -description

The expression evaluator interface to the underlying debugger.


## -inheritance
IDebugHostEvaluator interits from IUnknown. 
## -members

<p>IDebugHostEvaluator has these methods.</p>
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
		<td>EvaluateExpression</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>EvaluateExtendedExpression</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

One of the most important pieces of functionality which the debug host provides to clients is access to its language based expression evaluator. The IDebugHostEvaluator and IDebugHostEvaluator2 interfaces are the means to access that functionality from the debug host. 

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
