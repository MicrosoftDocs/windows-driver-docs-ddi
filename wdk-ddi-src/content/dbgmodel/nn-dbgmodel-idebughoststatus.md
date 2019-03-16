---
UID: NN:dbgmodel.IDebugHostStatus
title: IDebugHostStatus (dbgmodel.h)
description: An interface allowing a client to query for the status of the host.
ms.assetid: aff0759f-6583-437e-a68d-793566b83eed
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
- apiref
api_type: 
- COM
api_location: 
- dbgmodel.h
api_name: 
- IDebugHostStatus
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostStatus interface

## -description

An interface allowing a client to query for the status of the host.

The IDebugHostStatus interface allows a client of the data model or the debug host to inquire about certain aspects of the debug host's status. 

## -inheritance
IDebugHostStatus interits from IUnknown. 
## -members

<p>IDebugHostStatus has these methods.</p>
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
		<td>PollUserInterrupt</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
