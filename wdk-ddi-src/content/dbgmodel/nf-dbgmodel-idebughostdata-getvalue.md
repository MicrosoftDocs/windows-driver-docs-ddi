---
UID: NF:dbgmodel.IDebugHostData.GetValue
title: IDebugHostData::GetValue (dbgmodel.h)
description: Returns the value of the constant in a VARIANT data structure.
ms.assetid: f36dd267-59f8-41aa-99ae-455ae6e98c1e
ms.date: 09/10/2018
f1_keywords:
 - "dbgmodel/IDebugHostData.GetValue"
ms.keywords: IDebugHostData::GetValue, GetValue, IDebugHostData.GetValue, IDebugHostData::GetValue, IDebugHostData.GetValue
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
- IDebugHostData.GetValue
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostData::GetValue


## -description

Returns the value of the constant in a VARIANT data structure.

## -parameters

### -param value
The value of the data packed into a VARIANT will be returned here.

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostData> spData; /* get a data symbol */

VARIANT vtValue;
if (SUCCEEDED(spData->GetValue(&vtValue)))
{
    // For data which has a constant value as determined by GetLocationKind, 
    // vtValue contains the value of the data
    VariantClear(&vtValue);
}
```

## -see-also
[IDebugHostData interface](nn-dbgmodel-idebughostdata.md)
