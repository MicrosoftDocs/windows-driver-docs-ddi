---
UID: NF:wdfchildlist.WdfChildListRetrieveNextDevice
title: WdfChildListRetrieveNextDevice function
author: windows-driver-content
description: The WdfChildListRetrieveNextDevice method traverses a specified child list and retrieves the next child device that matches specified criteria.
old-location: wdf\wdfchildlistretrievenextdevice.htm
old-project: wdf
ms.assetid: 925807ff-e445-4ccf-ace6-fd913439799b
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFDeviceObjectChildListRef_c7ac1028-c3a3-4189-ae63-510bd199fcb2.xml, WdfChildListRetrieveNextDevice, WdfChildListRetrieveNextDevice method, kmdf.wdfchildlistretrievenextdevice, wdf.wdfchildlistretrievenextdevice, wdfchildlist/WdfChildListRetrieveNextDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfchildlist.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
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
apiname:
-	WdfChildListRetrieveNextDevice
product: Windows
targetos: Windows
req.typenames: WDF_RETRIEVE_CHILD_FLAGS
req.product: Windows 10 or later.
---

# WdfChildListRetrieveNextDevice function


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WdfChildListRetrieveNextDevice</b> method traverses a specified child list and retrieves the next child device that matches specified criteria.


## -syntax


````
NTSTATUS WdfChildListRetrieveNextDevice(
  _In_    WDFCHILDLIST             ChildList,
  _In_    PWDF_CHILD_LIST_ITERATOR Iterator,
  _Out_   WDFDEVICE                *Device,
  _Inout_ PWDF_CHILD_RETRIEVE_INFO Info
);
````


## -parameters




### -param ChildList [in]

A handle to a framework child-list object.


### -param Iterator [in]

A pointer to the same caller-allocated <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_list_iterator.md">WDF_CHILD_LIST_ITERATOR</a> structure that the driver previously supplied to <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginiteration.md">WdfChildListBeginIteration</a>.


### -param Device [out]

A pointer to a location that receives a handle to a framework device object. The received value is <b>NULL</b> if the <i>Iterator</i> parameter specifies the <a href="..\wdfchildlist\ne-wdfchildlist-_wdf_retrieve_child_flags.md">WdfRetrievePendingChildren</a> flag.


### -param Info [in, out]

A pointer to a caller-allocated <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_retrieve_info.md">WDF_CHILD_RETRIEVE_INFO</a> structure. This pointer is optional and can be <b>NULL</b>.


## -returns



<b>WdfChildListRetrieveNextDevice</b> returns STATUS_SUCCESS, or another status value for which <a href="https://msdn.microsoft.com/fe823930-e3ff-4c95-a640-bb6470c95d1d">NT_SUCCESS(status)</a> equals <b>TRUE</b>, if the operation succeeds. Otherwise, this method might return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An input parameter was invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>
</td>
<td width="60%">
The size of the <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_list_iterator.md">WDF_CHILD_LIST_ITERATOR</a> structure that <i>Iterator</i> specified was incorrect

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
An address description was specified but the child list did not contain address descriptions.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_MORE_ENTRIES</b></dt>
</dl>
</td>
<td width="60%">
The framework reached the end of the child list.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_STATE</b></dt>
</dl>
</td>
<td width="60%">
The driver has not called <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginiteration.md">WdfChildListBeginIteration</a>.

</td>
</tr>
</table>
 

This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.



A system bug check occurs if the driver supplies an invalid object handle.





## -remarks



Before calling <b>WdfChildListRetrieveNextDevice</b>, your driver must call <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginiteration.md">WdfChildListBeginIteration</a>. After the driver has finished traversing the child list, it must call <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistenditeration.md">WdfChildListEndIteration</a>. The framework then informs the Plug and Play (PnP) manager of any changes that were made to the child list.

Each time the driver calls <b>WdfChildListRetrieveNextDevice</b>, the method retrieves the next child that matches the following search criteria:

<ul>
<li>
The child's type must correspond to <a href="..\wdfchildlist\ne-wdfchildlist-_wdf_retrieve_child_flags.md">WDF_RETRIEVE_CHILD_FLAGS</a>-typed flags in the driver's <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_list_iterator.md">WDF_CHILD_LIST_ITERATOR</a> structure.

</li>
<li>
If the driver provides a pointer to an <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_compare.md">EvtChildListIdentificationDescriptionCompare</a> callback function in its <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_retrieve_info.md">WDF_CHILD_RETRIEVE_INFO</a> structure, the callback function must return <b>TRUE</b>.

</li>
</ul>
If the driver provides an <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_compare.md">EvtChildListIdentificationDescriptionCompare</a> callback function, it must also provide an <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">identification description</a> in the WDF_CHILD_RETRIEVE_INFO structure. The framework uses the callback function to compare the passed-in identification descriptor with a child's description in the child list, if the WDF_RETRIEVE_CHILD_FLAGS-typed flags indicate that the child is a match candidate. If the callback function returns <b>TRUE</b>, the match is successful. If the callback function returns <b>FALSE</b>, the framework looks for another candidate.

When <b>WdfChildListRetrieveNextDevice</b> finds a match, it copies the child's identification description and address description into the driver's <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_retrieve_info.md">WDF_CHILD_RETRIEVE_INFO</a> structure, if the pointer that the <i>Info</i> parameter specifies is not <b>NULL</b>. (Note that this operation overwrites the driver's input identification description.) The method also places a handle to the child's device object in the location that the <i>Device</i> parameter identifies.

For more information about child lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.


#### Examples

The following code example informs the framework that all of a parent device's children are being ejected. The example obtains a device's default child list and walks through the list. It obtains each child's identification descriptor, and it passes each identification descriptor to <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistrequestchildeject.md">WdfChildListRequestChildEject</a>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>WDF_CHILD_LIST_ITERATOR  iterator;
WDFDEVICE  hChild;
NTSTATUS  status = STATUS_INVALID_PARAMETER;
WDFCHILDLIST  list;
WDF_CHILD_RETRIEVE_INFO  childInfo;
PDO_IDENTIFICATION_DESCRIPTION  description;
BOOLEAN  ret;

list = WdfFdoGetDefaultChildList(Device);

WDF_CHILD_LIST_ITERATOR_INIT(
                             &amp;iterator,
                             WdfRetrievePresentChildren
                             );
WdfChildListBeginIteration(
                           list,
                           &amp;iterator
                           );
for (;;) {
    WDF_CHILD_RETRIEVE_INFO_INIT(
                                 &amp;childInfo,
                                 &amp;description.Header
                                 );
    WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT(
                                                     &amp;description.Header,
                                                     sizeof(description)
                                                     );
    status = WdfChildListRetrieveNextDevice(
                                            list, 
                                            &amp;iterator, 
                                            &amp;hChild, 
                                            &amp;childInfo
                                            );
    if (!NT_SUCCESS(status) || status == STATUS_NO_MORE_ENTRIES) {
       break;
    }
    ASSERT(childInfo.Status == WdfChildListRetrieveDeviceSuccess);

    ret = WdfChildListRequestChildEject(
                                        list,
                                        &amp;description.Header
                                        );
    if(!ret) {
       WDFVERIFY(ret);
    }
}
WdfChildListEndIteration(
                         list,
                         &amp;iterator
                         );
if (status == STATUS_NO_MORE_ENTRIES) {
   status = STATUS_SUCCESS;
}
return status;</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievenextdevice.md">WdfChildListRetrieveNextDevice</a>



<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginiteration.md">WdfChildListBeginIteration</a>



<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistbeginscan.md">WdfChildListBeginScan</a>



<a href="..\wdfchildlist\nf-wdfchildlist-wdf_child_identification_description_header_init.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT</a>



<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistenditeration.md">WdfChildListEndIteration</a>



<a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_compare.md">EvtChildListIdentificationDescriptionCompare</a>



<a href="..\wdfchildlist\nf-wdfchildlist-wdf_child_list_iterator_init.md">WDF_CHILD_LIST_ITERATOR_INIT</a>



<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistrequestchildeject.md">WdfChildListRequestChildEject</a>



<a href="..\wdfchildlist\ne-wdfchildlist-_wdf_retrieve_child_flags.md">WDF_RETRIEVE_CHILD_FLAGS</a>



<a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_list_iterator.md">WDF_CHILD_LIST_ITERATOR</a>



<a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_retrieve_info.md">WDF_CHILD_RETRIEVE_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfChildListRetrieveNextDevice method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

