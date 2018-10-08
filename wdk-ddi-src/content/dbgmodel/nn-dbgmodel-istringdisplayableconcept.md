---
UID: NN:dbgmodel.IStringDisplayableConcept
title: IStringDisplayableConcept
author: windows-driver-content
description: Interface which clients must implement on any object which is convertible to a display string.
ms.assetid: 108b4841-40cd-4771-ac66-953c9910b143
ms.author: windowsdriverdev
ms.date: 10/05/2018
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
-	IStringDisplayableConcept
product: Windows
targetos: Windows
tech.root: debugger
---

# IStringDisplayableConcept interface

## -description

Interface which clients must implement on any object which is convertible to a display string.

Clients should not rely on the form of this string conversion for programmatic purposes.  It is intended for display purposes only.

## -inheritance
IStringDisplayableConcept interits from IUnknown. 

## -members

<p>IStringDisplayableConcept has these methods.</p>
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
		<td>ToDisplayString</td>
		<td>TBD</td>
	</tr>
</table>

## -remarks

An object which wishes to provide a string conversion for display purposes can implement the string displayable concept through implementation of the IStringDisplayableConcept interface. 

## -see-also

[Debugger Data Model C++ Overview](https://docs.microsoft.com/windows-hardware/drivers/debugger/data-model-cpp-overview)
