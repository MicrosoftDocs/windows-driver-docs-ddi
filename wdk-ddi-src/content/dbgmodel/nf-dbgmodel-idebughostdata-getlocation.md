---
UID: NF:dbgmodel.IDebugHostData.GetLocation
title: IDebugHostData::GetLocation (dbgmodel.h)
description: For data which has an address, the GetLocation method will return the abstract location (address) of the field.
ms.date: 09/10/2018
keywords: ["IDebugHostData::GetLocation"]
ms.keywords: IDebugHostData::GetLocation, GetLocation, IDebugHostData.GetLocation, IDebugHostData::GetLocation, IDebugHostData.GetLocation
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
 - IDebugHostData::GetLocation
 - dbgmodel/IDebugHostData::GetLocation
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostData.GetLocation
---

# IDebugHostData::GetLocation


## -description

For data which has an address, the GetLocation method will return the abstract location (address) of the field. 
If the given data does not have a static location, the GetLocation method will fail.

## -parameters

### -param location

The abstract location (e.g.: address) of the data will be returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostData> spData; /* get a data symbol */

Location dataLocation;
if (SUCCEEDED(spData->GetLocation(&dataLocation)))
{
    // For data which has a static location as determined by 
    // GetLocationKind, dataLocation contains the location of the data
}
```

## -see-also

[IDebugHostData interface](nn-dbgmodel-idebughostdata.md)

