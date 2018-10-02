---
UID: NF:dbgmodel.IDebugHostSymbols.CreateTypeSignature
title: IDebugHostSymbols::CreateTypeSignature
author: windows-driver-content
description: TBD
ms.assetid: ead25214-26a0-4819-81ca-e47f5644b1f2
ms.author: windowsdriverdev
ms.date: 08/22/2018
ms.topic: method
ms.keywords: IDebugHostSymbols::CreateTypeSignature, CreateTypeSignature, IDebugHostSymbols.CreateTypeSignature, IDebugHostSymbols::CreateTypeSignature, IDebugHostSymbols.CreateTypeSignature
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
-	IDebugHostSymbols.CreateTypeSignature
product: Windows
targetos: Windows
tech.root: debugger
---

# IDebugHostSymbols::CreateTypeSignature


## -description

The CreateTypeSignature method creates a signature which can be used to match a set of concrete types by containing module and type name. The format of the type name signature string is specific to the language being debugged (and debug host). For C/C++, the signature string is equivalent to a NatVis Type Specification. That is, the signature string is a type name where wildcards (specified as *) are allowed for template arguments. 

## -parameters

### -param signatureSpecification
The signature string which identifies the types to which this signature applies. The format of this string is specific to the language being debugged. For C/C++, this is equivalent to a NatVis type specification. Such is a type name where wildcards are allowed for template arguments (specified as a *).


### -param module
If specified, only types which are contained within the given module match the signature. If not specified, types in any module can potentially match the signature.

### -param typeSignature
The created type signature object is returned here.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHost> spHost; /* get the host */

ComPtr<IDebugHostSymbols> spSym;
if (SUCCEEDED(spHost.As(&spSym)))
{
    // Create a type signature for MyTemplateType<*>
    ComPtr<IDebugHostTypeSignature> spSig1;
    if (SUCCEEDED(spSym->CreateTypeSignature(L"MyTemplateType<*>", 
                                             nullptr, 
                                             &spSig1)))
    {
        // spSig1 is a type signature which will match any concrete template 
        // type with a base name of MyTemplateType and *ANY* template arguments.
        // This is true regardless of the module in which the type is contained.
    }

    ComPtr<IDebugHostModule> spMyModule;
    if (SUCCEEDED(spSym->FindModuleByName(USE_CURRENT_HOST_CONTEXT, 
                                          L"MyModule.dll", 
                                          &spMyModule)))
    {
        // Create a type signature for MyTemplateType<*> within MyModule.dll.
        ComPtr<IDebugHostTypeSignature> spSig2;
        if (SUCCEEDED(spSym->CreateTypeSignature(L"MyTemplateType<*>", 
                                                 nullptr, 
                                                 &spSig2)))
        {
            // spSig2 is a type signature which will match any concrete 
            // template type with a base name of MyTemplateType and *ANY* 
            // template arguments that is within the particular MyModule.dll 
            // that's in the current UI context (e.g.: process) of the debugger.
            // This means if the host is debugging multiple processes
            // and you switch processes, a MyTemplateType<*> in an identically
            // named and versioned MyModule.dll will *NOT* match this signature.
        }
    }
}
```


## -see-also
[IDebugHostSymbols interface](nn-dbgmodel-idebughostsymbols.md)
