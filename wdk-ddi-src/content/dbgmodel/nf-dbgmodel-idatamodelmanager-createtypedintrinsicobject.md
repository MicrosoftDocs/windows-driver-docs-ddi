---
UID: NF:dbgmodel.IDataModelManager.CreateTypedIntrinsicObject
title: IDataModelManager::CreateTypedIntrinsicObject (dbgmodel.h)
description: The CreateTypedintrinsicObject method is similar to the CreateIntrinsicObject method excepting that it allows a native/language type to be associated with the data and carried along with the boxed value.
ms.assetid: 389a450e-6cea-408e-aeaa-ff90b572158c
ms.date: 07/17/2018
ms.topic: method
f1_keywords:
 - "dbgmodel/IDataModelManager.CreateTypedIntrinsicObject"
ms.keywords: IDataModelManager::CreateTypedIntrinsicObject, CreateTypedIntrinsicObject, IDataModelManager.CreateTypedIntrinsicObject, IDataModelManager::CreateTypedIntrinsicObject, IDataModelManager.CreateTypedIntrinsicObject
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
- IDataModelManager.CreateTypedIntrinsicObject
product:
- Windows
targetos: Windows
tech.root: debugger
ms.custom: RS5
---

# IDataModelManager::CreateTypedIntrinsicObject

## -description

The CreateTypedintrinsicObject method is similar to the CreateIntrinsicObject method excepting that it allows a native/language type to be associated with the data and carried along with the boxed value. This allows the data model to represent constructs such as native enumeration types (which are simply VT_UI* or VT_I* values). Pointer types are also created with this method. A native pointer in the data model is a zero extended 64-bit quantity representing an offset into the virtual address space of the debug target. It is boxed inside a VT_UI8 and is created with this method and a type which indicates a native/language pointer. 

## -parameters

### -param intrinsicData
A VARIANT containing the value which is going to be boxd inside an [IModelObject](nn-dbgmodel-imodelobject.md) container. Note that this method does not support VT_UNKNOWN constructs. Anything passed to this method must be expressable as ObjectIntrinsic.

### -param type
The native/language type of the value.

### -param object
The newly boxed value (as an [IModelObject](nn-dbgmodel-imodelobject.md)) will be returned here.


## -returns
This method returns HRESULT that indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDataModelManager> spManager; /* get the data model manager */
ComPtr<IDebugHostType> spEnumType;   /* get an enum type (see CreateTypedObject) */
ComPtr<IDebugHostType> spPtrType;    /* get a pointer type (see CreateTypedObject) */

// Box an enum
VARIANT vtEnumValue;
vtEnumValue.vt = VT_I4;
vtEnumValue.lVal = 2;

ComPtr<IModelObject> spEnumValue;
if (SUCCEEDED(spManager->CreateTypedIntrinsicObject(&vtEnumValue, 
                                                    spEnumType.Get(), 
                                                    &spEnumValue)))
{
    // spEnumValue now contains the value '2' expressed as the enum type 
    // in spEnumType.  The value will still present as 2 and operate as any other int.
    // A type query on the object will, however, yield the enum type.
}

// Box a pointer.  All pointers are represented as unsigned 64-bit values.  
// 32-bit pointers are **ZERO EXTENDED** to 64-bits.
VARIANT vtPtrValue;
vtPtrValue.vt = VT_UI8;
vtPtrValue.ullVal = 0x100; // the pointer address

ComPtr<IModelObject> spPtrValue;
if (SUCCEEDED(spManager->CreateTypedIntrinsicObject(&vtPtrValue, spPtrType.Get(), &spPtrValue)))
{
    // spPtrValue now contains a <TYPE (POINTER)>(0x100).  You can fetch 
    // the pointer address through standard means of GetIntrinsicValue(As).
    // Dereference() will work on spPtrValue!
}
```



## -see-also

[IDataModelManager interface](nn-dbgmodel-idatamodelmanager.md)
