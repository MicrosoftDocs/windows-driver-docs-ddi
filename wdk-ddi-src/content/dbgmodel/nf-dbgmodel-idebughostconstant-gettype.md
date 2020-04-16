---
UID: NF:dbgmodel.IDebugHostConstant.GetType
title: IDebugHostConstant::GetType (dbgmodel.h)
description: Returns the type (that is "int *") of the symbol if the symbol has a type.
ms.assetid: 1cde171b-5adb-4447-b423-313874706cf3
ms.date: 09/21/2018
keywords: ["IDebugHostConstant::GetType"]
f1_keywords:
 - "dbgmodel/IDebugHostConstant.GetType"
ms.keywords: IDebugHostConstant::GetType, GetType, IDebugHostConstant.GetType, IDebugHostConstant::GetType, IDebugHostConstant.GetType
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
- apiref
api_type: 
- COM
api_location: 
- dbgmodel.h
api_name: 
- IDebugHostConstant.GetType
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostConstant::GetType


## -description
Returns the type (e.g.: "int *") of the symbol if the symbol has a type.  If the symbol does not have a type, an error is returned.
 
## -parameters

### -param type
The type of the symbol will be returned here.

## -returns
This method returns HRESULT that indicates success or failure.


## -returns
This method returns HRESULT.
## -remarks

## -see-also
[IDebugHostConstant interface](nn-dbgmodel-idebughostconstant.md)
