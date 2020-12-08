---
UID: NF:wdfcollection.WdfCollectionGetLastItem
title: WdfCollectionGetLastItem function (wdfcollection.h)
description: The WdfCollectionGetLastItem method returns a handle to the last object that is in an object collection.
old-location: wdf\wdfcollectiongetlastitem.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfCollectionGetLastItem function"]
ms.keywords: DFCollectionObjectRef_1c6d4bbf-6d37-4b27-8421-df1ce61888ef.xml, WdfCollectionGetLastItem, WdfCollectionGetLastItem method, kmdf.wdfcollectiongetlastitem, wdf.wdfcollectiongetlastitem, wdfcollection/WdfCollectionGetLastItem
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
 - WdfCollectionGetLastItem
 - wdfcollection/WdfCollectionGetLastItem
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
 - WdfCollectionGetLastItem
---

# WdfCollectionGetLastItem function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfCollectionGetLastItem</b> method returns a handle to the last object that is in an object collection.

## -parameters

### -param Collection 

[in]
A handle to a collection object.

## -returns

<b>WdfCollectionGetLastItem</b> returns a handle to the object that is currently at the end of the specified collection's list of objects, or <b>NULL</b> if the list is empty.

A bug check occurs if the driver supplies an invalid object handle.

## -remarks

For more information about object collections, see <a href="/windows-hardware/drivers/wdf/framework-object-collections">Framework Object Collections</a>.


#### Examples

The following code example obtains a handle to the last object that is in an object collection.

```cpp
WDFOBJECT lastItem;

lastItem = WdfCollectionGetLastItem(hCollection);
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfcollection/nf-wdfcollection-wdfcollectiongetfirstitem">WdfCollectionGetFirstItem</a>



<a href="/windows-hardware/drivers/ddi/wdfcollection/nf-wdfcollection-wdfcollectiongetitem">WdfCollectionGetItem</a>
