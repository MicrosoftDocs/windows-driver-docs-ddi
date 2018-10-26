---
UID: NF:dbgmodel.IDebugHostType.GetMemberType
title: IDebugHostType::GetMemberType
author: windows-driver-content
description: For types which are pointer-to-member (as indicated by a type kind of TypeMemberPointer), the GetMemberType method returns the class the pointer is a pointer-to-member of. 
ms.assetid: baa26552-7b8d-444f-984a-51e9af4c4336
ms.date: 08/22/2018
ms.topic: method
ms.keywords: IDebugHostType::GetMemberType, GetMemberType, IDebugHostType.GetMemberType, IDebugHostType::GetMemberType, IDebugHostType.GetMemberType
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
-	apiref
api_type: 
-	COM
api_location: 
-	dbgmodel.h
api_name: 
-	IDebugHostType.GetMemberType
product: Windows
targetos: Windows
tech.root: debugger
---

# IDebugHostType::GetMemberType


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

ComPtr<IDebugHostType> spType;
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

[IDebugHostType interface](nn-dbgmodel-idebughosttype.md)
