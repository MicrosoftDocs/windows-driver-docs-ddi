---
UID: NF:dbgmodel.IDebugHostSymbols.EnumerateModules
title: IDebugHostSymbols::EnumerateModules (dbgmodel.h)
description: The EnumerateModules method creates an enumerator which will enumerate every module available in a particular host context.
ms.assetid: 1eb51e30-762b-4c52-9297-52a620fd8104
ms.date: 08/22/2018
keywords: ["IDebugHostSymbols::EnumerateModules"]
ms.keywords: IDebugHostSymbols::EnumerateModules, EnumerateModules, IDebugHostSymbols.EnumerateModules, IDebugHostSymbols::EnumerateModules, IDebugHostSymbols.EnumerateModules
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
 - IDebugHostSymbols::EnumerateModules
 - dbgmodel/IDebugHostSymbols::EnumerateModules
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostSymbols.EnumerateModules
---

# IDebugHostSymbols::EnumerateModules


## -description

The EnumerateModules method creates an enumerator which will enumerate every module available in a particular host context. That host context might encapsulate a process context or it might encapsulate something like the Windows kernel.

## -parameters

### -param context

The host context for which to enumerate every loaded module.

### -param moduleEnum

An enumerator which will enumerate every module loaded into the given context will be returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDebugHost> spHost; /* get the host */

ComPtr<IDebugHostSymbols> spSym;
if (SUCCEEDED(spHost.As(&spSym)))
{
    // Enumerate all modules in the current UI context (process) of the debug host:
    ComPtr<IDebugHostSymbolEnumerator> spEnum;
    if (SUCCEEDED(spSym->EnumerateModules(USE_CURRENT_HOST_CONTEXT, &spEnum)))
    {
        HRESULT hr = S_OK;
        while (SUCCEEDED(hr))
        {
            ComPtr<IDebugHostSymbol> spModSym;
            hr = spEnum->GetNext(&spModSym);
            if (SUCCEEDED(hr))
            {
                ComPtr<IDebugHostModule> spModule;
                if (SUCCEEDED(spModSym.As(&spModule))) /* should always succeed */
                {
                    // spModule is one of the modules in the current
                    // UI context (process) of the debug host
                }
            }
        }

        // hr == E_BOUNDS : hit the end of the enumerator
        // hr == E_ABORT  : a user interrupt was requested / 
        //                  propagate upwards immediately
    }
}
```

## -see-also

[IDebugHostSymbols interface](nn-dbgmodel-idebughostsymbols.md)

