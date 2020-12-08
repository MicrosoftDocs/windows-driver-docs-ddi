---
UID: NF:wdfcollection.WdfCollectionGetItem
title: WdfCollectionGetItem function (wdfcollection.h)
description: The WdfCollectionGetItem method returns a handle to the object that is contained in a specified object collection and associated with a specified index value.
old-location: wdf\wdfcollectiongetitem.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfCollectionGetItem function"]
ms.keywords: DFCollectionObjectRef_8476d0ef-d5e3-4dbc-95de-bbabd04c22bc.xml, WdfCollectionGetItem, WdfCollectionGetItem method, kmdf.wdfcollectiongetitem, wdf.wdfcollectiongetitem, wdfcollection/WdfCollectionGetItem
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
 - WdfCollectionGetItem
 - wdfcollection/WdfCollectionGetItem
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
 - WdfCollectionGetItem
---

# WdfCollectionGetItem function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfCollectionGetItem</b> method returns a handle to the object that is contained in a specified object collection and associated with a specified index value.

## -parameters

### -param Collection 

[in]
A handle to a collection object.

### -param Index 

[in]
A zero-based index value that identifies an object in the collection.

## -returns

<b>WdfCollectionGetItem</b> returns a framework object handle, or <b>NULL</b> if the <i>Index</i> value is invalid.

A system bug check occurs if the driver supplies an invalid object handle.

## -remarks

Index values represent the order in which objects are added to a collection. An index value of zero represents the first object in the collection, an index value of one represents the second object, and so on, like a linked list. When the driver removes item <i>i</i> from a collection, item <i>i</i>+1 becomes item <i>i</i>. 

For more information about object collections, see <a href="/windows-hardware/drivers/wdf/framework-object-collections">Framework Object Collections</a>.


#### Examples

For a code example that uses <b>WdfCollectionGetItem</b>, see <a href="/windows-hardware/drivers/ddi/wdfcollection/nf-wdfcollection-wdfcollectiongetcount">WdfCollectionGetCount</a>.

```cpp

```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfcollection/nf-wdfcollection-wdfcollectiongetfirstitem">WdfCollectionGetFirstItem</a>



<a href="/windows-hardware/drivers/ddi/wdfcollection/nf-wdfcollection-wdfcollectiongetlastitem">WdfCollectionGetLastItem</a>
