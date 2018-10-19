---
UID: NN:dbgmodel.IDebugHostErrorSink
title: IDebugHostErrorSink
author: windows-driver-content
description: An interface to which errors will be sinked.
ms.assetid: b82fbfe5-75c6-4c4c-8670-c2021dfa4c0d
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
-	IDebugHostErrorSink
product: Windows
targetos: Windows
tech.root: debugger
---

# IDebugHostErrorSink interface

## -description

An interface to which errors will be sinked.

An interface implemented by callers to receive errors from certain portions of the host and data model.


## -inheritance
IDebugHostErrorSink interits from IUnknown. 
## -members

<p>IDebugHostErrorSink has these methods.</p>
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

The IDebugHostErrorSink is a means by which a client can receive notifications of errors which occur during certain operations and route those errors where needed. 

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
