---
UID: NF:dbgmodel.IDebugHostBaseClass.GetType
title: IDebugHostBaseClass::GetType (dbgmodel.h)
description: Returns the type (that is "int *") of the symbol if the symbol has a type.
ms.assetid: ebf8fe3d-bd5d-4fdb-8ce7-0baca3149fb5
ms.date: 09/21/2018
ms.topic: method
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
topic_type: 
- apiref
api_type: 
- COM
api_location: 
- dbgmodel.h
api_name: 
- IDebugHostBaseClass.GetType
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
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
