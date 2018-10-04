---
UID: NF:dbgmodel.IDebugHostSymbols.CreateTypeSignatureForModuleRange
title: IDebugHostSymbols::CreateTypeSignatureForModuleRange
author: windows-driver-content
description: The CreateTypeSignatureForModuleRange method creates a signature which can be used to match a set of concrete types by module signature and type name. 
ms.assetid: fee485a1-0e7b-4af3-9a2c-b241c59fec5e
ms.author: windowsdriverdev
ms.date: 08/22/2018
ms.topic: method
ms.keywords: IDebugHostSymbols::CreateTypeSignatureForModuleRange, CreateTypeSignatureForModuleRange, IDebugHostSymbols.CreateTypeSignatureForModuleRange, IDebugHostSymbols::CreateTypeSignatureForModuleRange, IDebugHostSymbols.CreateTypeSignatureForModuleRange
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
-	IDebugHostSymbols.CreateTypeSignatureForModuleRange
product: Windows
targetos: Windows
tech.root: debugger
---

# IDebugHostSymbols::CreateTypeSignatureForModuleRange


## -description

The CreateTypeSignatureForModuleRange method creates a signature which can be used to match a set of concrete types by module signature and type name. This is similar to the CreateTypeSignature method excepting that instead of passing a specific module to match for the signature, the caller passes the arguments necessary to create a module signature (as if the module signature were created with the CreateModuleSignature method). 

## -parameters

### -param signatureSpecification
The signature string which identifies the types to which this signature applies. The format of this string is specific to the language being debugged. For C/C++, this is equivalent to a NatVis type specification. Such is a type name where wildcards are allowed for template arguments (specified as a *).

### -param moduleName
The name that the containing module must match (case insensitive) in order for the type to be considered a match for the signature.

### -param minVersion
The minimum version of the containing module for the type to be considered a match for the signature. The format of this argument is equivalent to the same argument in CreateModuleSignature

### -param maxVersion
The maximum version of the containing module for the type to be considered a match for the signature. The format of this argument is equivalent to the same argument in CreateModuleSignature

### -param typeSignature
The newly created type signature object will be returned here.

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHost> spHost; /* get the host */

ComPtr<IDebugHostSymbols> spSym;
if (SUCCEEDED(spHost.As(&spSym)))
{
    ComPtr<IDebugHostTypeSignature> spSig;
    if (SUCCEEDED(spSym->CreateTypeSignatureForModuleRange(
        L"MyTemplateType<*>", 
        L"MyModule.dll", 
        L"6.3", 
        L"10.0.0.0", 
        &spSig)))
    {
        // spSig is a type signature which will match any template type with 
        // a base name of MyTemplateType and *ANY* template arguments that is 
        // within a module named "MyModule.dll" with a version >= 6.3(.0.0) 
        // and a version <= 10.0.0.0 (regardless of the process/context of the module)
        //
        // Note that the version arguments are optional.  If absent, it indicates 
        // there is either no lower or no upper bound on the module version 
        // to match the signature.
    }
}
```

## -see-also
[IDebugHostSymbols interface](nn-dbgmodel-idebughostsymbols.md)
