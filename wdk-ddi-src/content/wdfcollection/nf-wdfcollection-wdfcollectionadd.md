---
UID: NF:wdfcollection.WdfCollectionAdd
title: WdfCollectionAdd function
author: windows-driver-content
description: The WdfCollectionAdd method adds a specified framework object to an object collection.
old-location: wdf\wdfcollectionadd.htm
old-project: wdf
ms.assetid: eed2ed36-c081-44c7-857b-d2a9f608a022
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: PFN_WDFCOLLECTIONADD, wdf.wdfcollectionadd, WdfCollectionAdd, WdfCollectionAdd method, kmdf.wdfcollectionadd, DFCollectionObjectRef_76895387-58f4-46fc-b5d0-244408fe57b9.xml, wdfcollection/WdfCollectionAdd
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
-	WdfCollectionAdd
product: Windows
targetos: Windows
req.typenames: "*PWDF_CHILD_RETRIEVE_INFO, WDF_CHILD_RETRIEVE_INFO"
req.product: Windows 10 or later.
---

# WdfCollectionAdd function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfCollectionAdd</b> method adds a specified framework object to an object collection. 


## -syntax


````
NTSTATUS WdfCollectionAdd(
  _In_ WDFCOLLECTION Collection,
  _In_ WDFOBJECT     Object
);
````


## -parameters




#### - Collection [in]

A handle to a collection object.


#### - Object [in]

A handle to the framework object that will be added to the collection.


## -returns


<b>WdfCollectionAdd</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The specified object could not be added to the specified collection.

</td>
</tr>
</table> 

This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.



## -remarks


The <b>WdfCollectionAdd</b> method appends the specified object to the end of the set of objects that the collection contains. When <b>WdfCollectionAdd</b> adds an object to a collection, it increments the object's reference count. Your driver can call <a href="..\wdfcollection\nf-wdfcollection-wdfcollectionremove.md">WdfCollectionRemove</a> or <a href="..\wdfcollection\nf-wdfcollection-wdfcollectionremoveitem.md">WdfCollectionRemoveItem</a> to remove the object and decrement its reference count. 

For more information about object collections, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/framework-object-collections">Framework Object Collections</a>.



## -see-also

<a href="..\wdfcollection\nf-wdfcollection-wdfcollectionremoveitem.md">WdfCollectionRemoveItem</a>

<a href="..\wdfcollection\nf-wdfcollection-wdfcollectionremove.md">WdfCollectionRemove</a>

<a href="..\wdfcollection\nf-wdfcollection-wdfcollectioncreate.md">WdfCollectionCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfCollectionAdd method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

