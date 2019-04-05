---
UID: NF:dbgmodel.IDebugHost.GetCurrentContext
title: IDebugHost::GetCurrentContext (dbgmodel.h)
description: The GetCurrentContext method returns an interface which represents the current state of the debugger host.
ms.assetid: 44829ee3-ae2f-4fed-9b80-6de77044a731
ms.date: 08/14/2018
ms.topic: method
ms.keywords: IDebugHost::GetCurrentContext, GetCurrentContext, IDebugHost.GetCurrentContext, IDebugHost::GetCurrentContext, IDebugHost.GetCurrentContext
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
- IDebugHost.GetCurrentContext
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDebugHost::GetCurrentContext


## -description

The GetCurrentContext method returns an interface which represents the current state of the debugger host. The exact meaning of this is left up to the host, but it typically includes things such as the session, process, and address space that is active in the user interface of the debug host. The returned context object is largely opaque to the caller but it is an important object to pass between calls to the debug host. When a caller is, for instance, reading memory, it is important to know which process and address space that memory is being read from. That notion is encapsulated in the notion of the context object which is returned from this method. 

Every object and symbol in the data model optionally has context information such as this associated with it. It is also often typical that context is passed from one object to new objects created as properties of existing ones. Such objects which are created by the debug host itself may cause additional context information to be embedded within the returned object (e.g.: the Stack property of a thread may embed information about which thread the stack refers to within the context). 


## -parameters

### -param context
An object representing the current context of the host is returned here.

## -returns
This method returns HRESULT which indicates success or failure. A host which does not have a concept of context information may return E_NOTIMPL here.

## -remarks

**Code Sample**

```cpp
ComPtr<IDebugHost> spHost; /* get the debug host */

ComPtr<IDebugHostContext> spContext;
if (SUCCEEDED(spHost->GetCurrentContext(&spContext)))
{
    // spContext now contains an opaque object representing the current UI 
    // state of the debugger (e.g.: what session/process/thread the debug UI 
    // is focused on)
}
```

## -see-also

[IDebugHost interface](nn-dbgmodel-idebughost.md)
