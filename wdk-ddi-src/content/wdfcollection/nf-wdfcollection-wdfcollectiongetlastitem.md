---
UID: NF:wdfcollection.WdfCollectionGetLastItem
title: WdfCollectionGetLastItem function
author: windows-driver-content
description: The WdfCollectionGetLastItem method returns a handle to the last object that is in an object collection.
old-location: wdf\wdfcollectiongetlastitem.htm
old-project: wdf
ms.assetid: f90732ab-3756-46e2-8a15-e94ff82b3548
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfCollectionGetLastItem method, wdfcollection/WdfCollectionGetLastItem, kmdf.wdfcollectiongetlastitem, WdfCollectionGetLastItem, PFN_WDFCOLLECTIONGETLASTITEM, wdf.wdfcollectiongetlastitem, DFCollectionObjectRef_1c6d4bbf-6d37-4b27-8421-df1ce61888ef.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfCollectionGetLastItem
product: Windows
targetos: Windows
req.typenames: "*PWDF_CHILD_RETRIEVE_INFO, WDF_CHILD_RETRIEVE_INFO"
req.product: Windows 10 or later.
---

# WdfCollectionGetLastItem function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfCollectionGetLastItem</b> method returns a handle to the last object that is in an object collection.


## -syntax


````
WDFOBJECT WdfCollectionGetLastItem(
  _In_ WDFCOLLECTION Collection
);
````


## -parameters




### -param Collection [in]

A handle to a collection object.


## -returns


<b>WdfCollectionGetLastItem</b> returns a handle to the object that is currently at the end of the specified collection's list of objects, or <b>NULL</b> if the list is empty.

A bug check occurs if the driver supplies an invalid object handle.



## -remarks


For more information about object collections, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/framework-object-collections">Framework Object Collections</a>.



## -see-also

<a href="..\wdfcollection\nf-wdfcollection-wdfcollectiongetfirstitem.md">WdfCollectionGetFirstItem</a>

<a href="..\wdfcollection\nf-wdfcollection-wdfcollectiongetitem.md">WdfCollectionGetItem</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfCollectionGetLastItem method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

