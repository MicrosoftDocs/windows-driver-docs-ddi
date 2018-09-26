---
UID: NF:dbgmodel.IDebugHostType2.GetGenericArgumentCount
title: IDebugHostType2::GetGenericArgumentCount
author: windows-driver-content
description: TBD
ms.assetid: 5ae39f4b-c5cf-4e46-800a-1577c86e5602
ms.author: windowsdriverdev
ms.date: 09/20/2018  
ms.topic: method
ms.keywords: IDebugHostType2::GetGenericArgumentCount, GetGenericArgumentCount, IDebugHostType2.GetGenericArgumentCount, IDebugHostType2::GetGenericArgumentCount, IDebugHostType2.GetGenericArgumentCount
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
-	IDebugHostType2.GetGenericArgumentCount
product: Windows
targetos: Windows


tech.root: debugger
---

# IDebugHostType2::GetGenericArgumentCount


## -description

Returns the number of arguments to the generic/template.  The returned value must be greater than zero.

## -parameters

### -param argCount
The number of generic arguments (e.g.: template arguments) to the type will be returned here.



## -returns
This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also
[IDebugHostType2 interface](nn-dbgmodel-idebughosttype2.md)
