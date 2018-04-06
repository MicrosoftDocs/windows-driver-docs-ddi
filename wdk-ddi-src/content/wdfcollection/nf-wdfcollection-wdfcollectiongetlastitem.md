---
UID: NF:wdfcollection.WdfCollectionGetLastItem
title: WdfCollectionGetLastItem function
author: windows-driver-content
description: The WdfCollectionGetLastItem method returns a handle to the last object that is in an object collection.
old-location: wdf\wdfcollectiongetlastitem.htm
old-project: wdf
ms.assetid: f90732ab-3756-46e2-8a15-e94ff82b3548
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFCollectionObjectRef_1c6d4bbf-6d37-4b27-8421-df1ce61888ef.xml, WdfCollectionGetLastItem, WdfCollectionGetLastItem method, kmdf.wdfcollectiongetlastitem, wdf.wdfcollectiongetlastitem, wdfcollection/WdfCollectionGetLastItem
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfCollectionGetLastItem
product:
- Windows
targetos: Windows
req.typenames: WDF_CHILD_RETRIEVE_INFO, *PWDF_CHILD_RETRIEVE_INFO
req.product: Windows 10 or later.
---

# WdfCollectionGetLastItem function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfCollectionGetLastItem</b> method returns a handle to the last object that is in an object collection.


## -parameters




### -param Collection [in]

A handle to a collection object.


## -returns



<b>WdfCollectionGetLastItem</b> returns a handle to the object that is currently at the end of the specified collection's list of objects, or <b>NULL</b> if the list is empty.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks



For more information about object collections, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/framework-object-collections">Framework Object Collections</a>.


#### Examples

The following code example obtains a handle to the last object that is in an object collection.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDFOBJECT lastItem;

lastItem = WdfCollectionGetLastItem(hCollection);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545763">WdfCollectionGetFirstItem</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545770">WdfCollectionGetItem</a>
 

 

