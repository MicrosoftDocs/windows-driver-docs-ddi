---
UID: NF:dbgmodel.IDebugHostSymbols.FindModuleByName
title: IDebugHostSymbols::FindModuleByName (dbgmodel.h)
description: The FindModuleByName method will look through the given host context and locate a module which has the specified name and return an interface to it.
ms.date: 11/10/2020
keywords: ["IDebugHostSymbols::FindModuleByName"]
ms.keywords: IDebugHostSymbols::FindModuleByName, FindModuleByName, IDebugHostSymbols.FindModuleByName, IDebugHostSymbols::FindModuleByName, IDebugHostSymbols.FindModuleByName
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
 - IDebugHostSymbols::FindModuleByName
 - dbgmodel/IDebugHostSymbols::FindModuleByName
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostSymbols::FindModuleByName
---

# IDebugHostSymbols::FindModuleByName


## -description

The FindModuleByName method will look through the given host context and locate a module which has the specified name and return an interface to it. It is legal to search for the module by name with or without the file extension.

## -parameters

### -param context

This host context will be searched for a loaded module matching the given name.

### -param moduleName

The name of the module to search for. The name may be specified with or without a file extension.

### -param module

If the module is found, an interface to the module will be returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHost> spHost; /* get the host */

ComPtr<IDebugHostSymbols> spSym;
if (SUCCEEDED(spHost.As(&spSym)))
{
    // Find the "notepad.exe" module in the current UI context (process) 
    // of the debug host:
    ComPtr<IDebugHostModule> spModule;
    if (SUCCEEDED(spSym->FindModuleByName(USE_CURRENT_HOST_CONTEXT, 
                                          L"notepad.exe", 
                                          &spModule)))
    {
        // spModule is the module "notepad.exe"
    }
}
```

**Differences in symbol module matching in FindModuleByName, CreateTypeSignature and CreateTypeSignatureForModuleRange**

FindModuleByName will allow the passed module name to be either the module's real image name for example My Module.dll, or the one that you can reference it by in the debugger engine (e.g.: MyModule or MyModule_\<hex_base\>).

Calling [CreateTypeSignatureForModuleRange](nf-dbgmodel-idebughostsymbols-createtypesignatureformodulerange.md) and passing a name/nullptr/nullptr will create a signature that will match any module that matches that name of any version.

The module name passed to the [CreateTypeSignature](nf-dbgmodel-idebughostsymbols-createtypesignature.md)  functions will only accept the module's real image name (e.g.: MyModule.dll).

Calling FindModuleByName and then CreateTypeSignature with that module will create a signature that will match only the particular instance of the module passed to it. If there's two copies of a module that is loaded (e.g.: ntdll in a 32-bit process running on 64-bit Windows), it would only match the specific instance passed. It would also no longer match if that DLL were unloaded and reloaded. The signature is associated to a specific instance of a module as known by the debugger.

## -see-also

[IDebugHostSymbols interface](nn-dbgmodel-idebughostsymbols.md)

[CreateTypeSignature](nf-dbgmodel-idebughostsymbols-createtypesignature.md)  

[CreateTypeSignatureForModuleRange](nf-dbgmodel-idebughostsymbols-createtypesignatureformodulerange.md)

