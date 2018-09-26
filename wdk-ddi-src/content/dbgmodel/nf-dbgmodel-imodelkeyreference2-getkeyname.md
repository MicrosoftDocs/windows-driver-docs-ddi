---
UID: NF:dbgmodel.IModelKeyReference2.GetKeyName
title: IModelKeyReference2::GetKeyName
author: windows-driver-content
description: TBD
ms.assetid: bfb61278-8eac-47e5-9900-aed8b31370c5
ms.author: windowsdriverdev
ms.date: 08/14/2018
ms.topic: method
ms.keywords: IModelKeyReference2::GetKeyName, GetKeyName, IModelKeyReference2.GetKeyName, IModelKeyReference2::GetKeyName, IModelKeyReference2.GetKeyName
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
-	IModelKeyReference2.GetKeyName
product: Windows
targetos: Windows


tech.root: debugger
---

# IModelKeyReference2::GetKeyName


## -description

The GetKeyName method returns the name of the key to which this key reference is a handle. The returned string is a standard BSTR and must be freed via a call to SysFreeString. 

## -parameters

### -param keyName
The name of the key to which this key reference is a handle will be returned here as an allocated string.

## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Code Sample**

```cpp
ComPtr<IModelObject> spObject; /* get an object */

ComPtr<IModelKeyReference> spKeyRef;
if (SUCCEEDED(spObject->GetKeyReference(L"Id", &spKeyRef, nullptr)))
{
    // The key reference is a reference to the Id key.  The name returned 
    // should be "Id"
    BSTR returnedKeyName;
    if (SUCCEEDED(spKeyRef->Getname(&returnedKeyName)))
    {
        // returnedKeyName is "Id"
        SysFreeString(returnedKeyName);
    }
}
```

## -see-also

[IModelKeyReference2 interface](nn-dbgmodel-imodelkeyreference2.md)
