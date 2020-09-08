---
UID: NF:dbgmodel.IDebugHostModuleSignature.IsMatch
title: IDebugHostModuleSignature::IsMatch (dbgmodel.h)
description: The IsMatch method compares a particular module against a signature, comparing the module name and version to the name and version range indicated in the signature.
ms.assetid: eaef18a0-1bbb-4248-a65d-e81ef486c2fa
ms.date: 09/18/2018
keywords: ["IDebugHostModuleSignature::IsMatch"]
ms.keywords: IDebugHostModuleSignature::IsMatch, IsMatch, IDebugHostModuleSignature.IsMatch, IDebugHostModuleSignature::IsMatch, IDebugHostModuleSignature.IsMatch
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
 - IDebugHostModuleSignature::IsMatch
 - dbgmodel/IDebugHostModuleSignature::IsMatch
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostModuleSignature.IsMatch
---

# IDebugHostModuleSignature::IsMatch


## -description

The IsMatch method compares a particular module (as given by an [IDebugHostModule](nn-dbgmodel-idebughostmodule.md) symbol) against a signature, comparing the module name and version to the name and version range indicated in the signature. An indication of whether the given module symbol matches the signature is returned.

## -parameters

### -param pModule

The module symbol to compare against the module signature.

### -param isMatch

An indication of whether the given module symbol matches the module signature is returned here.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHostSymbols> spSym;   /* get the host's symbols interface */
ComPtr<IDebugHostModule> spModule; /* find a module */

ComPtr<IDebugHostModuleSignature> spModuleSignature;
if (SUCCEEDED(spSym->CreateModuleSignature(
    L"Windows.UI.Xaml.dll", 
    L"6.3", 
    nullptr, 
    &spModuleSignature)))
{
    bool isMatch;
    if (SUCCEEDED(spModuleSignature->IsMatch(spModule.Get(), &isMatch)))
    {
        // isMatch indicates whether the module is a match for the signature.  
        // In this case, that means the module is named Windows.UI.Xaml.dll 
        // and the version is at least 6.3(.0.0).
    }
}
```

## -see-also

[IDebugHostModuleSignature interface](nn-dbgmodel-idebughostmodulesignature.md)

