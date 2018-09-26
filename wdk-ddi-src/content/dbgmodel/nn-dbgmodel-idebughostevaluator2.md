---
UID: NN:dbgmodel.IDebugHostEvaluator2
title: IDebugHostEvaluator2
author: windows-driver-content
description: TBD
ms.assetid: 12192b1b-57b6-4a5b-b2a9-2de8e13ea5c3
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
-	IDebugHostEvaluator2
product: Windows
targetos: Windows
tech.root: debugger
---

# IDebugHostEvaluator2 interface

## -description

The expression evaluator interface to the underlying debugger.


## -inheritance
IDebugHostEvaluator2 interits from IDebugHostEvaluator. 
## -members

<p>IDebugHostEvaluator2 has these methods.</p>
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
	<tr>
		<td>AssignTo</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

One of the most important pieces of functionality which the debug host provides to clients is access to its language based expression evaluator. The IDebugHostEvaluator and IDebugHostEvaluator2 interfaces are the means to access that functionality from the debug host. 

## -see-also

[Debugger Data Model C++ Overview](https://review.docs.microsoft.com/en-us/windows-hardware/drivers/debugger/data-model-cpp-overview?branch=debugger-op-ref-docs)
