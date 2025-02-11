---
UID: NF:dbgmodel.IDebugHostType3.GetIntrinsicType
tech.root: debugger
title: IDebugHostType3::GetIntrinsicType
ms.date: 01/26/2025
targetos: Windows
description: The GetIntrinsicType method, when called on a type, gets information about what kind of intrinsic the type is.
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
 - IDebugHostType3::GetIntrinsicType
f1_keywords:
 - IDebugHostType3::GetIntrinsicType
 - dbgmodel/IDebugHostType3::GetIntrinsicType
dev_langs:
 - c++
helpviewer_keywords:
 - GetIntrinsicType
---

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

[IDebugHostType3 interface](nn-dbgmodel-idebughosttype3.md)
