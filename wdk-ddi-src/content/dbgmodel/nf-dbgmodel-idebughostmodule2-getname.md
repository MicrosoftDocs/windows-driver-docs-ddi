---
UID: NF:dbgmodel.IDebugHostModule2.GetName
title: IDebugHostModule2::GetName (dbgmodel.h)
description: "The IDebugHostModule2::GetName method, when called on a symbol, gets the name of the symbol if it has a name."
ms.date: 09/18/2018
keywords: ["IDebugHostModule2::GetName"]
ms.keywords: IDebugHostModule2::GetName, GetName, IDebugHostModule2.GetName, IDebugHostModule2::GetName, IDebugHostModule2.GetName
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
 - IDebugHostModule2::GetName
 - dbgmodel/IDebugHostModule2::GetName
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostModule2::GetName
---

# IDebugHostModule2::GetName


## -description

Returns the name of the symbol if the symbol has a name.  If the symbol does not have a name, an error is returned.

## -parameters

### -param symbolName

The name of the symbol will be returned here as a string allocated via the SysAllocString method.  The caller is responsible for freeing the allocated string via the SysFreeString method.

## -returns

This method returns HRESULT that indicates success or failure.

## -see-also

[IDebugHostModule2 interface](nn-dbgmodel-idebughostmodule2.md)

