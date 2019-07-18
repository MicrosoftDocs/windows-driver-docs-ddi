---
UID: NF:dbgmodel.IDebugHost.GetHostDefinedInterface
title: IDebugHost::GetHostDefinedInterface (dbgmodel.h)
description: The GetHostDefinedInterface method returns the host's main private interface, if such exists for the given host. 
ms.assetid: 55ad88f7-ef21-40b8-a496-cb2d015080e5
ms.date: 08/14/2018
ms.topic: method
f1_keywords:
 - "dbgmodel/IDebugHost.GetHostDefinedInterface"
ms.keywords: IDebugHost::GetHostDefinedInterface, GetHostDefinedInterface, IDebugHost.GetHostDefinedInterface, IDebugHost::GetHostDefinedInterface, IDebugHost.GetHostDefinedInterface
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
- apiref
api_type: 
- COM
api_location: 
- dbgmodel.h
api_name: 
- IDebugHost.GetHostDefinedInterface
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHost::GetHostDefinedInterface


## -description

The GetHostDefinedInterface method returns the host's main private interface, if such exists for the given host. For Debugging Tools for Windows, the interface returned here is an IDebugClient (cast to IUnknown). 

## -parameters

### -param hostUnk
The debug host's core private interface is returned here. For Debugging Tools for Windows, this is an IDebugClient interface.

## -returns
This method returns HRESULT that indicates success or failure. A host which does not have a private interface that it wishes to expose to data model clients may return E_NOTIMPL here.

## -remarks

**Code Sample**

```cpp
ComPtr<IDebugHost> spHost; /* get the debug host */

// Get the debug host private interface back from the host interfaces.  
// This is **HOST SPECIFIC**
ComPtr<IUnknown> spPrivate;
if (SUCCEEDED(spHost->GetHostDefinedInterface(&spPrivate)))
{
    // As an example, consider DbgEng:
    ComPtr<IDebugClient> spClient;
    if (SUCCEEDED(spPrivate.As(&spClient)))
    {
        // spClient now contains a DbgEng IDebugClient!
    }
}
```

## -see-also

[IDebugHost interface](nn-dbgmodel-idebughost.md)
