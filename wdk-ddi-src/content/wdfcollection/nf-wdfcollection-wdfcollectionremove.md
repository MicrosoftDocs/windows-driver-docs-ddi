---
UID: NF:wdfcollection.WdfCollectionRemove
title: WdfCollectionRemove function
author: windows-driver-content
description: The WdfCollectionRemove method removes an object from a specified object collection.
old-location: wdf\wdfcollectionremove.htm
old-project: wdf
ms.assetid: 3a708949-3d4e-49b2-bef2-7151aec2b84b
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfCollectionRemove
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
req.alt-api: WdfCollectionRemove
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
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
req.typenames: *PWDF_CHILD_RETRIEVE_INFO, WDF_CHILD_RETRIEVE_INFO
req.product: Windows 10 or later.
---

# WdfCollectionRemove function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfCollectionRemove</b> method removes an object from a specified object collection.



## -syntax

````
VOID WdfCollectionRemove(
  _In_ WDFCOLLECTION Collection,
  _In_ WDFOBJECT     Item
);
````


## -parameters

### -param Collection [in]

A handle to a collection object.


### -param Item [in]

A handle to the framework object that will be removed from the collection.


## -returns
None.

A system bug check occurs if the driver supplies an invalid object handle.


## -remarks
When <b>WdfCollectionRemove</b> removes an object from a collection, it decrements the object's reference count. 

For more information about object collections, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/framework-object-collections">Framework Object Collections</a>.

The following code example removes a specified object from a specified object collection.


## -see-also
<dl>
<dt>
<a href="..\wdfcollection\nf-wdfcollection-wdfcollectionremoveitem.md">WdfCollectionRemoveItem</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfCollectionRemove method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

