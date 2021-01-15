---
UID: NF:dbgmodel.IDebugHostConstant.GetName
title: IDebugHostConstant::GetName (dbgmodel.h)
description: Returns the name of the symbol if the symbol has a name.
ms.date: 09/10/2018
keywords: ["IDebugHostConstant::GetName"]
ms.keywords: IDebugHostConstant::GetName, GetName, IDebugHostConstant.GetName, IDebugHostConstant::GetName, IDebugHostConstant.GetName
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
 - IDebugHostConstant::GetName
 - dbgmodel/IDebugHostConstant::GetName
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostConstant::GetName
---

# IDebugHostConstant::GetName


## -description

Returns the name of the symbol if the symbol has a name.  If the symbol does not have a name, an error is returned.

## -parameters

### -param symbolName

The name of the symbol will be returned here as a string allocated via the SysAllocString method.  The caller is responsible for freeing the allocated string via the SysFreeString method.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDebugHostConstant interface](nn-dbgmodel-idebughostconstant.md)

