---
UID: NF:dbgmodel.IDebugHostModule5.FindTypeByName
tech.root: debugger
title: IDebugHostModule5::FindTypeByName
ms.date: 02/24/2025
targetos: Windows
description: The IDebugHostModule5::FindTypeByName method, when called on a module, finds a type by type name from within the module and retrieves a type symbol for it.
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
 - IDebugHostModule5::FindTypeByName
f1_keywords:
 - IDebugHostModule5::FindTypeByName
 - dbgmodel/IDebugHostModule5::FindTypeByName
dev_langs:
 - c++
helpviewer_keywords:
 - FindTypeByName
---

## -description

The FindTypeByName method finds a type defined within the module by the type name and returns a type symbol for it. This method may return a valid [IDebugHostType](nn-dbgmodel-idebughosttype.md) which would never be returned via explicit recursion of children of the module. The debug host may allow creation of derivative types -- types not ever used within the module itself but derived from types that are. As an example, if the structure MyStruct is defined in the symbols of the module but the type MyStruct ** is never used, the FindTypeByName method may legitimately return a type symbol for MyStruct ** despite that type name never explicitly appearing in the symbols for the module. 

Many debug hosts will make an explicit attempt to contextualize the type name which is passed to the FindTypeByName method and find a matching type within the symbolic information according to the rules of the language and not a raw comparison against symbol names. In the event that a debug host is unable to do this, it will fall back to raw comparison against symbol names.

## -parameters

### -param typeName

The language type to find in the symbolic information for the module. The type may also be derived from (e.g.: be a pointer to or an array of) a type found in the symbolic information of the module.

### -param type

A type symbol for the found type will be returned here.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostModule5> spModule; /* get a module (see FindModuleByName) */

// Find "MyStruct **".  Note that only "MyStruct" might be in the symbols
ComPtr<IDebugHostType> spType;
if (SUCCEEDED(spModule->FindTypeByName(L"MyStruct **", &spType)))
{
    // spType contains a type symbol for "MyStruct **"
}
```

## -see-also

[IDebugHostModule5 interface](nn-dbgmodel-idebughostmodule5.md)
