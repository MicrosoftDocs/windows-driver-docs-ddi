---
UID: NF:dbgmodel.IDebugHostType.GetFunctionCallingConvention
title: IDebugHostType::GetFunctionCallingConvention
author: windows-driver-content
description: TBD
ms.assetid: 7c0b15e9-abd8-4b17-abc8-2212205875fa
ms.author: windowsdriverdev
ms.date: 08/22/2018
ms.topic: method
ms.keywords: IDebugHostType::GetFunctionCallingConvention, GetFunctionCallingConvention, IDebugHostType.GetFunctionCallingConvention, IDebugHostType::GetFunctionCallingConvention, IDebugHostType.GetFunctionCallingConvention
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
-	IDebugHostType.GetFunctionCallingConvention
product: Windows
targetos: Windows


---

# IDebugHostType::GetFunctionCallingConvention


## -description

The GetFunctionCallingConvention method returns the calling convention of the function. Such is returned as a member of the CallingConventionKind enumeration. 

## -parameters

### -param conventionKind
The calling convention of the function is returned here as a member of the CallingConventionKind enumeration.



## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```
```

## -see-also

[IDebugHostType interface](nn-dbgmodel-idebughosttype.md)