---
UID: NF:dbgmodel.IDebugHostPublic.GetLocationKind
title: IDebugHostPublic::GetLocationKind (dbgmodel.h)
description: "The IDebugHostPublic::GetLocationKind method, when called on a symbol, gets the kind of location the symbol is at according to the LocationKind enumeration."
ms.date: 09/18/2018
keywords: ["IDebugHostPublic::GetLocationKind"]
ms.keywords: IDebugHostPublic::GetLocationKind, GetLocationKind, IDebugHostPublic.GetLocationKind, IDebugHostPublic::GetLocationKind, IDebugHostPublic.GetLocationKind
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
 - IDebugHostPublic::GetLocationKind
 - dbgmodel/IDebugHostPublic::GetLocationKind
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostPublic::GetLocationKind
---

# IDebugHostPublic::GetLocationKind


## -description

The GetLocationKind method returns what kind of location the symbol is at according to the LocationKind enumeration. The description of this enumeration can be found in the documentation for [IDebugHostField](nn-dbgmodel-idebughostfield.md).

## -parameters

### -param locationKind

The kind of location for this field will be returned here as a value of the LocationKind enumeration.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostPublic> spPublic; /* get a public symbol (see EnumerateChildren) */

LocationKind kind;
if (SUCCEEDED(spPublic->GetLocationKind(&kind)))
{
    // kind indicates the kind of location (static, none).
}
```

## -see-also

[IDebugHostPublic interface](nn-dbgmodel-idebughostpublic.md)

