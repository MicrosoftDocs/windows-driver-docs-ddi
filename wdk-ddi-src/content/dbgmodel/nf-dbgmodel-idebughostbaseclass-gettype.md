---
UID: NF:dbgmodel.IDebugHostBaseClass.GetType
title: IDebugHostBaseClass::GetType (dbgmodel.h)
description: Returns the type (that is "int *") of the symbol if the symbol has a type.
ms.date: 09/21/2018
keywords: ["IDebugHostBaseClass::GetType"]
ms.keywords: IDebugHostBaseClass::GetType, GetType, IDebugHostBaseClass.GetType, IDebugHostBaseClass::GetType, IDebugHostBaseClass.GetType
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
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - IDebugHostBaseClass::GetType
 - dbgmodel/IDebugHostBaseClass::GetType
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostBaseClass::GetType
---

# IDebugHostBaseClass::GetType


## -description

Returns the type (e.g.: "int *") of the symbol if the symbol has a type.  If the symbol does not have a type, an error is returned.

## -parameters

### -param type

The type of the symbol will be returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -see-also

[IDebugHostBaseClass interface](nn-dbgmodel-idebughostbaseclass.md)

