---
UID: NF:dbgmodel.IDebugHostSymbols.CreateModuleSignature
title: IDebugHostSymbols::CreateModuleSignature
author: windows-driver-content
description: TBD
ms.assetid: e3cac74c-4c56-457f-bfec-522405553d68
ms.author: windowsdriverdev
ms.date: 08/22/2018
ms.topic: method
ms.keywords: IDebugHostSymbols::CreateModuleSignature, CreateModuleSignature, IDebugHostSymbols.CreateModuleSignature, IDebugHostSymbols::CreateModuleSignature, IDebugHostSymbols.CreateModuleSignature
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
-	IDebugHostSymbols.CreateModuleSignature
product: Windows
targetos: Windows


---

# IDebugHostSymbols::CreateModuleSignature


## -description

The CreateModuleSignature method creates a signature which can be used to match a set of specific modules by name and optionally, by version. There are three components to a module signature: 

- A name: a matching module must have a name which is an exact case insensitive match against the name in the signature

- A minimum version: if specified, a matching module must have a minimum version which is at least as high as this version. Versions are specified in "A.B.C.D" format with each subsequent portion being less important than the prior. Only the first segment is mandatory.

- A maximum version: if specified, a matching module must have a maximum version which is no higher than this version. Versions are specified in "A.B.C.D" format with each subsequent portion being less important than the prior. Only the first segment is mandatory.


## -parameters

### -param pwszModuleName
The name that a module must have in order to match the signature (case insensitive).

### -param pwszMinVersion
The minimum version that a module must have in order to match the signature. If this argument is nullptr, there is no minimum version required to match the signature. Versions are specified as strings in "A.B.C.D" format with only the first component being required and subsequent components being less important.

### -param pwszMaxVersion
The maximum version that a module can have in order to match the signature. If this argument is nullptr, there is no upper limit on version number required to match the signature. Versions are specified as strings in "A.B.C.D" format with only the first component being required and subsequent components being less important.

### -param ppModuleSignature
The created module signature object is returned here.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHost> spHost; /* get the host */

ComPtr<IDebugHostSymbols> spSym;
if (SUCCEEDED(spHost.As(&spSym)))
{
    ComPtr<IDebugHostModuleSignature> spBasicSignature;
    if (SUCCEEDED(spSym->CreateModuleSignature(
        L"Windows.UI.Xaml.dll", 
        nullptr, 
        nullptr, 
        &spBasicSignature)))
    {
        // spBasicSignature is a signature which will match any module 
        // named "Windows.UI.Xaml.dll" regardless of version.
    }

    ComPtr<IDebugHostModuleSignature> spVersionedSignature;
    if (SUCCEEDED(spSym->CreateModuleSignature(
        L"Windows.UI.Xaml.dll", 
        "6.3", 
        "10.0.0.0", 
        &spVersionedSignature)))
    {
        // spVersionedSignature is a signature which will match a module named
        // "Windows.UI.Xaml.dll" whose version is >= 6.3(.0.0) and whose 
        // version <= 10.0.0.0
    }
}
```

## -see-also

[IDebugHostSymbols interface](nn-dbgmodel-idebughostsymbols.md)
