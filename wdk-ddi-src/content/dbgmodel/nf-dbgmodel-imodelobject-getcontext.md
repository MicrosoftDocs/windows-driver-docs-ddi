---
UID: NF:dbgmodel.IModelObject.GetContext
title: IModelObject::GetContext (dbgmodel.h)
description: The GetContext method returns the host context that is associated with the object. 
ms.assetid: 448a54c8-ab67-4bc1-aad4-362ea94f7830
ms.date: 08/09/2018
f1_keywords:
 - "dbgmodel/IModelObject.GetContext"
ms.keywords: IModelObject::GetContext, GetContext, IModelObject.GetContext, IModelObject::GetContext, IModelObject.GetContext
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
- IModelObject.GetContext
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IModelObject::GetContext


## -description

The GetContext method returns the host context that is associated with the object. This represents which target, process, thread, etc... the object came from. 

## -parameters

### -param context
The host context of the object will be returned in this argument.

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks


**Code Sample**

```cpp
ComPtr<IDebugHost> spHost;      // get the debug host
ComPtr<IModelObject> spObject;  // get an object within a process (or a process object)

ComPtr<IDebugHostContext> spContext;
ComPtr<IDebugHostMemory> spMemory;
if (SUCCEEDED(spObject->GetContext(&spContext)) &&
    SUCCEEDED(spHost.As(&spMemory)))
{
    // Read 4 bytes from address 0x100 in the process context represented by spObject
    char bytes[4];
    ULONG64 bytesRead;
    HRESULT hr = spMemory->ReadBytes(spContext.Get(), 0x100, bytes, ARRAYSIZE(bytes), &bytesRead);
    
    // Check / Use read.
}
```

## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)
