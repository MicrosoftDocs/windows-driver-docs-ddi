---
UID: NF:dbgmodel.IModelObject.IsEqualTo
title: IModelObject::IsEqualTo (dbgmodel.h)
description: The IsEqualTo method compares a host context to another host context. If the two contexts are equivalent, an indication of this is returned. Note that this comparison is not interface equivalence.
ms.assetid: 06dd5b3c-8216-444b-82a7-dcfbf0361a30
ms.date: 08/13/2018
keywords: ["IModelObject::IsEqualTo"]
ms.keywords: IModelObject::IsEqualTo, IsEqualTo, IModelObject.IsEqualTo, IModelObject::IsEqualTo, IModelObject.IsEqualTo
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
 - IModelObject::IsEqualTo
 - dbgmodel/IModelObject::IsEqualTo
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IModelObject.IsEqualTo
---

# IModelObject::IsEqualTo


## -description

The IsEqualTo method compares a host context to another host context. If the two contexts are equivalent, an indication of this is returned. Note that this comparison is not interface equivalence. This compares the underlying opaque contents of the context itself. 

It is also important to note that this method checks for equivalence and not that one of the contexts is a subset or superset of the other.

## -parameters

### -param other

The host context to compare against.

### -param equal

An indication of whether the two contexts are equivalent is passed back here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

**Code Sample**

```cpp
ComPtr<IDebugHostContext> spContext1; /* get a context (e.g.:
                                         IDebugHost::GetCurrentContext) */
ComPtr<IDebugHostContext> spContext2; /* get another context (e.g.:
                                         IModelObject::GetContext) */

bool isEqual;
if (SUCCEEDED(spContext1->IsEqualTo(spContext2.Get(), &isEqual)) && isEqual)
{
    // The contexts are *IDENTICAL*
}
```

## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)

