---
UID: NF:dbgmodel.IKeyStore.ClearKeys
title: IKeyStore::ClearKeys
author: windows-driver-content
description: TBD
ms.assetid: 7fb81fa1-c09a-4995-9a28-34a2d5716625
ms.author: windowsdriverdev
ms.date: 08/13/2018
ms.topic: method
ms.keywords: IKeyStore::ClearKeys, ClearKeys, IKeyStore.ClearKeys, IKeyStore::ClearKeys, IKeyStore.ClearKeys
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
-	IKeyStore.ClearKeys
product: Windows
targetos: Windows
tech.root: debugger
---

# IKeyStore::ClearKeys


## -description

The ClearKeys method is analogous to the ClearKeys method on IModelObject. It will remove every key from the given metadata store. This method has no effect on any parent store. 

## -parameters


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Code Sample**

```cpp
ComPtr<IKeyStore> spMetadata; /* get a metadata store */

if (SUCCEEDED(spMetadata->ClearKeys()))
{
    // The metadata store is now empty.  A parent store may still have keys 
    // and GetKey[Value] may find those keys and values.
}
```

## -see-also

[IKeyStore interface](nn-dbgmodel-ikeystore.md)
