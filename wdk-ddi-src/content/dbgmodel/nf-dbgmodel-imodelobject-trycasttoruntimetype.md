---
UID: NF:dbgmodel.IModelObject.TryCastToRuntimeType
title: IModelObject::TryCastToRuntimeType (dbgmodel.h)
description: The TryCastToRuntimeType method will ask the debug host to perform an analysis and determine the actual runtime type (most derived class) of the given object.
ms.assetid: a65187dd-e6eb-4749-afa0-18ed308b416f
ms.date: 08/13/2018
ms.topic: method
ms.keywords: IModelObject::TryCastToRuntimeType, TryCastToRuntimeType, IModelObject.TryCastToRuntimeType, IModelObject::TryCastToRuntimeType, IModelObject.TryCastToRuntimeType
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
- IModelObject.TryCastToRuntimeType
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IModelObject::TryCastToRuntimeType


## -description

The TryCastToRuntimeType method will ask the debug host to perform an analysis and determine the actual runtime type (e.g.: most derived class) of the given object. The exact analysis utilized is specific to the debug host and may include RTTI (C++ run time type information), examination of the V-Table(virtual function table) structure of the object, or any other means that the host can use to reliably determine dynamic/runtime type from the static type. Failure to convert to a runtime type does not mean that this method call will fail. In such cases, the method will return the given object (the this pointer) in the output argument. 

## -parameters

### -param runtimeTypedObject
The conversion of the given object to an instance of its dynamic/runtime type will be returned in this argument. If analysis fails to find a change in static type, the given object (this pointer) maybe returned (with an additional reference) in this output.

## -returns
This method returns HRESULT that indicates success or failure. Note that an analysis which cannot find a derived type is not a failure as defined here.

## -remarks

**Code Sample**

```cpp
ComPtr<IModelObject> spUnknown; /* get an IUnknown pointer to some CFoo */

ComPtr<IModelObject> spRuntimeObj;
if (SUCCEEDED(spUnknown->TryCastToRuntimeType(&spRuntimeObj)))
{
    // spRuntimeObj will refer to the CFoo.
}
```


## -see-also

[IModelObject interface](nn-dbgmodel-imodelobject.md)
