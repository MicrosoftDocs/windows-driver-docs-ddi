---
UID: NF:dbgmodel.IModelObject.GetTargetInfo
title: IModelObject::GetTargetInfo (dbgmodel.h)
description: The GetTargetInfo method is effectively a combination of the GetLocation and GetTypeInfo methods returning both the abstract location as well as native type of the given object. 
ms.assetid: 01e44c1d-a96d-4195-a767-d959cccb005c
ms.date: 08/09/2018
ms.topic: method
ms.keywords: IModelObject::GetTargetInfo, GetTargetInfo, IModelObject.GetTargetInfo, IModelObject::GetTargetInfo, IModelObject.GetTargetInfo
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
-	IModelObject.GetTargetInfo
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IModelObject::GetTargetInfo


## -description

The GetTargetInfo method is effectively a combination of the GetLocation and GetTypeInfo methods returning both the abstract location as well as native type of the given object. 

## -parameters

### -param location
The abstract location of the native object represented by the this pointer will be returned here.

### -param type
The native type of the object represented by the this pointer will be returned here as an IDebugHostType interface.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Code Sample**

```cpp
ComPtr<IModelObject> spObject; /* get an object */

Location loc;
ComPtr<IDebugHostType> spType;
if (SUCCEEDED(spObject->GetTargetInfo(&loc, &spType)))
{
    // loc has a valid location
    // spType has a valid type -- the type of the object
}
```


## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)
