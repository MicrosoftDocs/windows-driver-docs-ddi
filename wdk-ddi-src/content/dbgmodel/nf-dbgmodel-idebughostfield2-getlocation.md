---
UID: NF:dbgmodel.IDebugHostField2.GetLocation
tech.root: debugger
title: IDebugHostField2::GetLocation
ms.date: 01/29/2025
targetos: Windows
description: For fields which have an address regardless of the particular type instance (e.g. fields whose location kind indicates LocationStatic), the GetLocation method will return the abstract location (address) of the field.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dbgmodel.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostField2::GetLocation
f1_keywords:
 - IDebugHostField2::GetLocation
 - dbgmodel/IDebugHostField2::GetLocation
dev_langs:
 - c++
helpviewer_keywords:
 - GetLocation
---

## -description

For fields which have an address regardless of the particular type instance (e.g. fields whose location kind indicates LocationStatic), the GetLocation method will return the abstract location (address) of the field.

If the given field does not have a static location, the GetLocation method will fail.

## -parameters

### -param location

The abstract location (e.g.: address) of the field will be returned here.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

**Sample Code***
```cpp
ComPtr<IDebugHostField> spField; /* get a field symbol (see EnumerateChildren) */

Location fieldLocation;
if (SUCCEEDED(spField->GetLocation(&fieldLocation)))
{
    // For fields which have a static location as determined by GetLocationKind, 
    // the location of the field will be in fieldLocation.
}
```

## -see-also

[IDebugHostField2 interface](nn-dbgmodel-idebughostfield2.md)
