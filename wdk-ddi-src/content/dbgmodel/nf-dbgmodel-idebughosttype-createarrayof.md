---
UID: NF:dbgmodel.IDebugHostType.CreateArrayOf
title: IDebugHostType::CreateArrayOf
author: windows-driver-content
description: TBD
ms.assetid: bb8de044-1e9d-4357-8419-44016942f386
ms.author: windowsdriverdev
ms.date: 08/22/2018
ms.topic: method
ms.keywords: IDebugHostType::CreateArrayOf, CreateArrayOf, IDebugHostType.CreateArrayOf, IDebugHostType::CreateArrayOf, IDebugHostType.CreateArrayOf
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
-	IDebugHostType.CreateArrayOf
product: Windows
targetos: Windows


---

# IDebugHostType::CreateArrayOf


## -description

For any given type, this returns a new IDebugHostType which is an array of this type.
The dimensions of the array must be supplied via the "dimensions" and "pDimensions" arguments.

## -parameters

### -param dimensions

### -param pDimensions

### -param newType



## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDebugHostType interface](nn-dbgmodel-idebughosttype.md)