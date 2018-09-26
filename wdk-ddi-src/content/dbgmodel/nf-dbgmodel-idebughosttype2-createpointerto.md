---
UID: NF:dbgmodel.IDebugHostType2.CreatePointerTo
title: IDebugHostType2::CreatePointerTo
author: windows-driver-content
description: TBD
ms.assetid: 52c9d51f-bda3-4599-904e-cd7fa27b0bfc
ms.author: windowsdriverdev
ms.date: 09/20/2018 
ms.topic: method
ms.keywords: IDebugHostType2::CreatePointerTo, CreatePointerTo, IDebugHostType2.CreatePointerTo, IDebugHostType2::CreatePointerTo, IDebugHostType2.CreatePointerTo
req.header: dbgmodel.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
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
-	IDebugHostType2.CreatePointerTo
product: Windows
targetos: Windows


tech.root: debugger
---

# IDebugHostType2::CreatePointerTo


## -description

For any given type, this returns a new IDebugHostType which is a pointer to this type.
The kind of pointer is supplied by the "kind" argument.

## -parameters

### -param kind
The kind of pointer to create (e.g.: a standard pointer, a C++ reference, a C++ rvalue reference, etc…)

### -param newType
The newly created pointer type will be returned here.


## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also
[IDebugHostType2 interface](nn-dbgmodel-idebughosttype2.md)
