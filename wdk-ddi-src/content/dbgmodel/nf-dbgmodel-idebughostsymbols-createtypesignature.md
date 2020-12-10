---
UID: NF:dbgmodel.IDebugHostSymbols.CreateTypeSignature
title: IDebugHostSymbols::CreateTypeSignature (dbgmodel.h)
description: The CreateTypeSignature method creates a signature which can be used to match a set of concrete types by containing module and type name.
ms.date: 11/10/2020
keywords: ["IDebugHostSymbols::CreateTypeSignature"]
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
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - IDebugHostSymbols::CreateTypeSignature
 - dbgmodel/IDebugHostSymbols::CreateTypeSignature
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostSymbols.CreateTypeSignature
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

**Differences in symbol module matching in FindModuleByName, CreateTypeSignature and CreateTypeSignatureForModuleRange**

[FindModuleByName](nf-dbgmodel-idebughostsymbols-findmodulebyname.md) will allow the passed module name to be either the module's real image name for example My Module.dll, or the one that you can reference it by in the debugger engine (e.g.: MyModule or MyModule_\<hex_base\>).

Calling [CreateTypeSignatureForModuleRange](nf-dbgmodel-idebughostsymbols-createtypesignatureformodulerange.md) and passing a name/nullptr/nullptr will create a signature that will match any module that matches that name of any version.

The module name passed to the CreateTypeSignature functions will only accept the module's real image name (e.g.: MyModule.dll).

Calling [FindModuleByName](nf-dbgmodel-idebughostsymbols-findmodulebyname.md) and then CreateTypeSignature with that module will create a signature that will match only the particular instance of the module passed to it. If there's two copies of a module that is loaded (e.g.: ntdll in a 32-bit process running on 64-bit Windows), it would only match the specific instance passed. It would also no longer match if that DLL were unloaded and reloaded. The signature is associated to a specific instance of a module as known by the debugger.

## -see-also

[IDebugHostSymbols interface](nn-dbgmodel-idebughostsymbols.md)

[FindModuleByName](nf-dbgmodel-idebughostsymbols-findmodulebyname.md)

[CreateTypeSignatureForModuleRange](nf-dbgmodel-idebughostsymbols-createtypesignatureformodulerange.md)
