---
UID: NF:dbgmodel.IDebugHostType2.GetMemberType
title: IDebugHostType2::GetMemberType (dbgmodel.h)
description: For types which are pointer-to-member (as indicated by a type kind of TypeMemberPointer), the GetMemberType method returns the class the pointer is a pointer-to-member of.
ms.assetid: 7813d8e7-962b-41e3-8635-9a9961952d05
ms.date: 09/20/2018
keywords: ["IDebugHostType2::GetMemberType"]
ms.keywords: IDebugHostType2::GetMemberType, GetMemberType, IDebugHostType2.GetMemberType, IDebugHostType2::GetMemberType, IDebugHostType2.GetMemberType
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
 - IDebugHostType2::GetMemberType
 - dbgmodel/IDebugHostType2::GetMemberType
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostType2.GetMemberType
---

# IDebugHostType2::GetMemberType


## -description

For types which are pointer-to-member (as indicated by a type kind of TypeMemberPointer), the GetMemberType method returns the class the pointer is a pointer-to-member of.

## -parameters

### -param memberType

The class that the pointer is a pointer-to-member of will be returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostModule> spModule; /* find some module */

ComPtr<IDebugHostType2> spType;
if (SUCCEEDED(spModule->FindTypeByName(L"int (MyClass::*)(int)", &spType)))
{
    // spType is a pointer-to-(MyClass)-member function taking int and returning int.
    ComPtr<IDebugHostType> spMemberType;
    if (SUCCEEDED(spType->GetMemberType(&spMemberType)))
    {
        // spMemberType is a type symbol for MyClass
    }
}
```

## -see-also

[IDebugHostType2 interface](nn-dbgmodel-idebughosttype2.md)

