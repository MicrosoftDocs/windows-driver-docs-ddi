---
UID: NF:dbgmodel.IDebugHostPublic.GetLocation
title: IDebugHostPublic::GetLocation (dbgmodel.h)
description: "The IDebugHostPublic::GetLocation method, when called on a symbol with a static location, gets the abstract location (address) of the symbol."
ms.date: 09/18/2018
keywords: ["IDebugHostPublic::GetLocation"]
ms.keywords: IDebugHostPublic::GetLocation, GetLocation, IDebugHostPublic.GetLocation, IDebugHostPublic::GetLocation, IDebugHostPublic.GetLocation
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
 - IDebugHostPublic::GetLocation
 - dbgmodel/IDebugHostPublic::GetLocation
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostPublic::GetLocation
---

# IDebugHostPublic::GetLocation


## -description

For data which has an address, the GetLocation method will return the abstract location (address) of the field. 

If the given public does not have a static location, the GetLocation method will fail.

## -parameters

### -param location

The abstract location (e.g.: address) of the data will be returned here.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostPublic> spPublic; /* get a public symbol (see EnumerateChildren) */

Location publicLocation;
if (SUCCEEDED(spPublic->GetLocation(&publicLocation)))
{
    // For public symbols which indicate they have a static location 
    // via GetLocationKind, publicLocation will be the location of the symbol
}

```

## -see-also

[IDebugHostPublic interface](nn-dbgmodel-idebughostpublic.md)

