---
UID: NF:dbgmodel.IDebugHostData.GetLocationKind
title: IDebugHostData::GetLocationKind (dbgmodel.h)
description: "The IDebugHostData::GetLocationKind method, when called on a symbol, gets the kind of location the symbol is at according to the LocationKind enumeration."
ms.date: 09/10/2018
keywords: ["IDebugHostData::GetLocationKind"]
ms.keywords: IDebugHostData::GetLocationKind, GetLocationKind, IDebugHostData.GetLocationKind, IDebugHostData::GetLocationKind, IDebugHostData.GetLocationKind
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
 - IDebugHostData::GetLocationKind
 - dbgmodel/IDebugHostData::GetLocationKind
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostData::GetLocationKind
---

# IDebugHostData::GetLocationKind


## -description

The GetLocationKind method returns what kind of location the symbol is at according to the LocationKind enumeration. The description of this enumeration can be found in the documentation for [IDebugHostField](nn-dbgmodel-idebughostfield.md).

## -parameters

### -param locationKind

The kind of location for this field will be returned here as a value of the LocationKind enumeration.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostData> spData; /* get a data symbol */

LocationKind kind;
if (SUCCEEDED(spData->GetLocationKind(&kind)))
{
    // kind indicates the kind of location (e.g.: static, constant, member, etc...)
}
```

## -see-also

[IDebugHostData interface](nn-dbgmodel-idebughostdata.md)

