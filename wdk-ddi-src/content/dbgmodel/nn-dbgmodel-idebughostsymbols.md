---
UID: NN:dbgmodel.IDebugHostSymbols
title: IDebugHostSymbols (dbgmodel.h)
description: The symbols interface to the underlying debugger.
ms.assetid: 9a26c85b-fc46-4a01-864d-c9c2fe51f9b3
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
-	IDebugHostSymbols
product: Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostSymbols interface

## -description

The symbols interface to the underlying debugger.

The IDebugHostSymbols interface is the main starting point to access symbols in the debug target. This interface can be queried from an instance of IDebugHost. 


## -inheritance
IDebugHostSymbols interits from IUnknown. 
## -members

<p>IDebugHostSymbols has these methods.</p>
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
		<td>CreateModuleSignature</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>CreateTypeSignature</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>CreateTypeSignatureForModuleRange</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>EnumerateModules</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>FindModuleByName</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>FindModuleByLocation</td>
		<td>TBD</td>
	</tr>
	<tr>
		<td>GetMostDerivedObject</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
