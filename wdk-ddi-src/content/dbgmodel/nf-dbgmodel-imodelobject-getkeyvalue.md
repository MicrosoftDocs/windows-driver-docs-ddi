---
UID: NF:dbgmodel.IModelObject.GetKeyValue
title: IModelObject::GetKeyValue
author: windows-driver-content
description: TBD
ms.assetid: 83daa8ab-3d90-4003-8ce9-7fe10acf2859
ms.author: windowsdriverdev
ms.date: 08/09/2018
ms.topic: method
ms.keywords: IModelObject::GetKeyValue, GetKeyValue, IModelObject.GetKeyValue, IModelObject::GetKeyValue, IModelObject.GetKeyValue
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
-	IModelObject.GetKeyValue
product: Windows
targetos: Windows
tech.root: debugger
---

# IModelObject::GetKeyValue


## -description

The GetKeyValue method is the first method a client will turn to in order to get the value of (and the metadata associated with) a given key by name. If the key is a property accessor -- that is it's value as an IModelObject which is a boxed IModelPropertyAccessor, the GetKeyValue method will automatically call the property accessor's GetValue method in order to retrieve the actual value. 

## -parameters

### -param key
The name of the key to get a value for.

### -param object
The value of the key will be returned in this argument. In some error cases, extended error information may be passed out in this argument even though the method returns a failing HRESULT.

### -param metadata
The metadata store associated with this key will be optionally returned in this argument.


## -returns
This method returns HRESULT that indicates success or failure. The return values E_BOUNDS (or E_NOT_SET in some cases) indicates the key could not be found.

## -remarks


**Code Sample**

```cpp
ComPtr<IModelObject> spProcess; /* get a process object */

ComPtr<IModelObject> spProcId;
if (SUCCEEDED(spProcess->GetKeyValue(L"Id", &spProcId, nullptr)))
{
    // spProcId has a boxed process id.  Use GetIntrinsicValueAs to unbox it.
}
```

## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)
