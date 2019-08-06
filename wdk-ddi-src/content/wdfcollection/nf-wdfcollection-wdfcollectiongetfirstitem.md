---
UID: NF:wdfcollection.WdfCollectionGetFirstItem
title: WdfCollectionGetFirstItem function (wdfcollection.h)
description: The WdfCollectionGetFirstItem method returns a handle to the first object that is in an object collection.
old-location: wdf\wdfcollectiongetfirstitem.htm
tech.root: wdf
ms.assetid: 4884de4d-6e5f-4c9f-bd49-2fc58481e9c6
ms.date: 02/26/2018
ms.keywords: DFCollectionObjectRef_1a816492-f120-48f9-9c10-88f71947008c.xml, WdfCollectionGetFirstItem, WdfCollectionGetFirstItem method, kmdf.wdfcollectiongetfirstitem, wdf.wdfcollectiongetfirstitem, wdfcollection/WdfCollectionGetFirstItem
ms.topic: function
f1_keywords:
 - "wdfcollection/WdfCollectionGetFirstItem"
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
- WdfCollectionGetFirstItem
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfCollectionGetFirstItem function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfCollectionGetFirstItem</b> method returns a handle to the first object that is in an object collection.


## -parameters




### -param Collection [in]

A handle to a collection object.


## -returns



<b>WdfCollectionGetFirstItem</b> returns a handle to the object that is currently at the front of the specified collection's list of objects, or <b>NULL</b> if the list is empty.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



For more information about object collections, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-collections">Framework Object Collections</a>.


#### Examples

The following code example removes each item from a collection and deletes each item's object.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>while ((subRequest = WdfCollectionGetFirstItem(hCollection)) != NULL) {
    WdfCollectionRemoveItem(
                            hCollection,
                            0
                            );
    WdfObjectDelete(subRequest);
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfcollection/nf-wdfcollection-wdfcollectiongetitem">WdfCollectionGetItem</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfcollection/nf-wdfcollection-wdfcollectiongetlastitem">WdfCollectionGetLastItem</a>
 

 

