---
UID: NF:dbgmodel.IDebugHostData.GetName
title: IDebugHostData::GetName (dbgmodel.h)
description: The GetLocationKind method returns what kind of location the symbol is at according to the LocationKind enumeration.
ms.date: 09/10/2018
keywords: ["IDebugHostData::GetName"]
ms.keywords: IDebugHostData::GetName, GetName, IDebugHostData.GetName, IDebugHostData::GetName, IDebugHostData.GetName
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
 - IDebugHostData::GetName
 - dbgmodel/IDebugHostData::GetName
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostData::GetName
---

# IDebugHostData::GetName


## -description

Returns the name of the symbol if the symbol has a name.  If the symbol does not have a name, an error is returned.

## -parameters

### -param symbolName

The name of the symbol will be returned here as a string allocated via the SysAllocString method.  The caller is responsible for freeing the allocated string via the SysFreeString method.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDebugHostData interface](nn-dbgmodel-idebughostdata.md)

