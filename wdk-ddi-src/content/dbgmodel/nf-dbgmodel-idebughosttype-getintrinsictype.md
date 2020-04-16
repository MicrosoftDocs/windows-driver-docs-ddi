---
UID: NF:dbgmodel.IDebugHostType.GetIntrinsicType
title: IDebugHostType::GetIntrinsicType (dbgmodel.h)
description: The GetIntrinsicType method returns information about what kind of intrinsic the type is.
ms.assetid: 8dc4ddeb-007b-4fe3-96b7-4f8278aec110
ms.date: 08/22/2018
keywords: ["IDebugHostType::GetIntrinsicType"]
f1_keywords:
 - "dbgmodel/IDebugHostType.GetIntrinsicType"
ms.keywords: IDebugHostType::GetIntrinsicType, GetIntrinsicType, IDebugHostType.GetIntrinsicType, IDebugHostType::GetIntrinsicType, IDebugHostType.GetIntrinsicType
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
- IDebugHostType.GetIntrinsicType
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHostType::GetIntrinsicType


## -description

The GetIntrinsicType method returns information about what kind of intrinsic the type is. Two values are returned out of this method: 

- The intrinsic kind indicates the overall type (e.g.: integer, unsigned, floating point) but not the size of the type (e.g.: 8 bit, 16 bit, 32 bit, 64 bit)

- The carrier type indicates how the intrinsic kind packs into a VARIANT structure. This is a VT_* constant.

The combination of the two values provides the full set of information about the intrinsic. 


## -parameters

### -param intrinsicKind
The kind of intrinsic will be returned here. This will indicate the overall type of the intrinsic -- whether it is an integer, unsigned, floating point, etc... It will not indicate the size of the intrinsic. 8, 16, 32, and 64 bit integers will be reported as signed integers -- nothing more.


### -param carrierType
A VT_* constant indicating how the intrinsic will pack into a VARIANT structure is returned here. This, combined with the value returned in the intrinsicKind argument gives the full information necessary to understand the nature of the intrinsic.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostType> spType; /* get a type (see FindTypeByName) for something 
                                  which is intrinsic (e.g.: an enum or ordinal) */

IntrinsicKind ik;
VARTYPE carrier;
if (SUCCEEDED(spType->GetIntrinsicType(&ik, &carrier)))
{
    // The type is defined by ik/carrier:
    //    e.g.: the C type "char" would be defined as IntrinsicChar / VT_I1.
    //    e.g.: the C type "wchar_t" would be defined as IntrinsicWChar / VT_UI2.
    //    e.g.: the C type "unsigned short" would be defined as IntrinsicUInt / VT_UI2.
    //    etc...
}
```

## -see-also

[IDebugHostType interface](nn-dbgmodel-idebughosttype.md)
