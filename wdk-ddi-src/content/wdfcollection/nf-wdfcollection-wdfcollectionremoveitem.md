---
UID: NF:wdfcollection.WdfCollectionRemoveItem
title: WdfCollectionRemoveItem function (wdfcollection.h)
description: The WdfCollectionRemoveItem method removes a specified object from an object collection, based on a specified index value.
old-location: wdf\wdfcollectionremoveitem.htm
tech.root: wdf
ms.assetid: 03fde4a7-a4d1-4045-ac0c-6a37f2367b9d
ms.date: 02/26/2018
ms.keywords: DFCollectionObjectRef_a037497e-b219-41c1-8d65-29cf8be17989.xml, WdfCollectionRemoveItem, WdfCollectionRemoveItem method, kmdf.wdfcollectionremoveitem, wdf.wdfcollectionremoveitem, wdfcollection/WdfCollectionRemoveItem
ms.topic: function
f1_keywords:
 - "wdfcollection/WdfCollectionRemoveItem"
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
- WdfCollectionRemoveItem
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfCollectionRemoveItem function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfCollectionRemoveItem</b> method removes a specified object from an object collection, based on a specified index value. 


## -parameters




### -param Collection [in]

A handle to a collection object.


### -param Index [in]

A zero-based index that identifies the object to remove. 


## -remarks

A bug check occurs if the driver supplies an invalid object handle.




Index values represent the order in which objects are added to a collection. An index value of zero represents the first object that was added to the collection, an index value of one represents the second object, and so on. 

When <b>WdfCollectionRemoveItem</b> removes an object from a collection, it decrements the object's reference count. 

For more information about object collections, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-collections">Framework Object Collections</a>



#### Examples

For a code example that uses <b>WdfCollectionRemoveItem</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfcollection/nf-wdfcollection-wdfcollectiongetfirstitem">WdfCollectionGetFirstItem</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfcollection/nf-wdfcollection-wdfcollectionremove">WdfCollectionRemove</a>
 

 

