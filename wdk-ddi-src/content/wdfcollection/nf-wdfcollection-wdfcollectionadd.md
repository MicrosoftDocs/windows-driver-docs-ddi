---
UID: NF:wdfcollection.WdfCollectionAdd
title: WdfCollectionAdd function
author: windows-driver-content
description: The WdfCollectionAdd method adds a specified framework object to an object collection.
old-location: wdf\wdfcollectionadd.htm
tech.root: wdf
ms.assetid: eed2ed36-c081-44c7-857b-d2a9f608a022
ms.date: 02/26/2018
ms.keywords: DFCollectionObjectRef_76895387-58f4-46fc-b5d0-244408fe57b9.xml, WdfCollectionAdd, WdfCollectionAdd method, kmdf.wdfcollectionadd, wdf.wdfcollectionadd, wdfcollection/WdfCollectionAdd
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
-	WdfCollectionAdd
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfCollectionAdd function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfCollectionAdd</b> method adds a specified framework object to an object collection. 


## -parameters




### -param Collection [in]

A handle to a collection object.


### -param Object [in]

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



The <b>WdfCollectionAdd</b> method appends the specified object to the end of the set of objects that the collection contains. When <b>WdfCollectionAdd</b> adds an object to a collection, it increments the object's reference count. Your driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff545784">WdfCollectionRemove</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff545792">WdfCollectionRemoveItem</a> to remove the object and decrement its reference count. 

For more information about object collections, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/framework-object-collections">Framework Object Collections</a>.


#### Examples

The following code example creates a collection object and then adds a set of driver-created request objects to the collection.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_OBJECT_ATTRIBUTES  attributes;
NTSTATUS  status;
WDFCOLLECTION  hCollection = NULL;
WDFREQUEST  subRequest = NULL;

WDF_OBJECT_ATTRIBUTES_INIT(&amp;attributes);
attributes.ParentObject = Request;
status = WdfCollectionCreate(
                             &amp;attributes,
                             &amp;hCollection
                             );
if (!NT_SUCCESS(status)) {
    goto Exit;
}

for (i = 0; i &lt; numSubRequests; i++) {
    WDF_OBJECT_ATTRIBUTES_INIT(&amp;attributes);
    WDF_OBJECT_ATTRIBUTES_SET_CONTEXT_TYPE(
                                           &amp;attributes,
                                           SUB_REQUEST_CONTEXT
                                           );
    status = WdfRequestCreate(
                              &amp;attributes,
                              WdfUsbTargetDeviceGetIoTarget(deviceContext-&gt;WdfUsbTargetDevice),
                              &amp;subRequest
                              );
    if (!NT_SUCCESS(status)) {
        goto Exit;
    }
    status = WdfCollectionAdd(
                              hCollection,
                              subRequest
                              );
    if (!NT_SUCCESS(status)) {
        WdfObjectDelete(subRequest);
        goto Exit;
    }
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545747">WdfCollectionCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545784">WdfCollectionRemove</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545792">WdfCollectionRemoveItem</a>
 

 

