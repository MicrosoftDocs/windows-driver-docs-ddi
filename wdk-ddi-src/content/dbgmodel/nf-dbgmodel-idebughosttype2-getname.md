---
UID: NF:dbgmodel.IDebugHostType2.GetName
title: IDebugHostType2::GetName
author: windows-driver-content
description: Returns the name of the symbol if the symbol has a name. 
ms.assetid: 45aec7db-0fcf-4344-ad6e-d680ea69cd45
ms.author: windowsdriverdev
ms.date: 09/21/2018 
ms.topic: method
ms.keywords: IDebugHostType2::GetName, GetName, IDebugHostType2.GetName, IDebugHostType2::GetName, IDebugHostType2.GetName
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
-	IDebugHostType2.GetName
product: Windows
targetos: Windows
tech.root: debugger
---

# IDebugHostType2::GetName


## -description

Returns the name of the symbol if the symbol has a name.  If the symbol does not have a name, an error is returned.


## -parameters

### -param symbolName
The name of the symbol will be returned here as a string allocated via the SysAllocString method.  The caller is responsible for freeing the allocated string via the SysFreeString method.

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also
[IDebugHostType2 interface](nn-dbgmodel-idebughosttype2.md)
