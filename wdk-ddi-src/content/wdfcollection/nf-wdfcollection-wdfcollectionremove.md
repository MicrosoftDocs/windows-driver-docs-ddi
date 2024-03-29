---
UID: NF:wdfcollection.WdfCollectionRemove
title: WdfCollectionRemove function (wdfcollection.h)
description: The WdfCollectionRemove method removes an object from a specified object collection.
old-location: wdf\wdfcollectionremove.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfCollectionRemove function"]
ms.keywords: DFCollectionObjectRef_ec848e8e-f64b-4f17-997a-0d9b6c509eb0.xml, WdfCollectionRemove, WdfCollectionRemove method, kmdf.wdfcollectionremove, wdf.wdfcollectionremove, wdfcollection/WdfCollectionRemove
req.header: wdfcollection.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfCollectionRemove
 - wdfcollection/WdfCollectionRemove
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
 - WUDFx02000.dll
 - WUDFx02000.dll.dll
api_name:
 - WdfCollectionRemove
---

# WdfCollectionRemove function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfCollectionRemove</b> method removes an object from a specified object collection.

## -parameters

### -param Collection [in]


A handle to a collection object.

### -param Item [in]


A handle to the framework object that will be removed from the collection.

## -remarks

A bug check occurs if the driver supplies an invalid object handle.




When <b>WdfCollectionRemove</b> removes an object from a collection, it decrements the object's reference count. 

For more information about object collections, see <a href="/windows-hardware/drivers/wdf/framework-object-collections">Framework Object Collections</a>.


#### Examples

The following code example removes a specified object from a specified object collection.

```cpp
WdfCollectionRemove(
                    hCollection,
                    hObject
                    );
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfcollection/nf-wdfcollection-wdfcollectionremoveitem">WdfCollectionRemoveItem</a>
