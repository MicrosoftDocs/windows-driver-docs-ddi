---
UID: NF:dbgmodel.IDebugHostType3.GetMemberType
tech.root: debugger
title: IDebugHostType3::GetMemberType
ms.date: 01/26/2025
targetos: Windows
description: The GetMemberType method, when called on a type for a pointer to a module member, gets the class of the module member.
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
 - IDebugHostType3::GetMemberType
f1_keywords:
 - IDebugHostType3::GetMemberType
 - dbgmodel/IDebugHostType3::GetMemberType
dev_langs:
 - c++
helpviewer_keywords:
 - GetMemberType
---

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

[IDebugHostType3 interface](nn-dbgmodel-idebughosttype3.md)

