---
UID: NF:wdfchildlist.WdfChildListRetrieveNextDevice
title: WdfChildListRetrieveNextDevice function (wdfchildlist.h)
description: The WdfChildListRetrieveNextDevice method traverses a specified child list and retrieves the next child device that matches specified criteria.
old-location: wdf\wdfchildlistretrievenextdevice.htm
tech.root: wdf
ms.assetid: 925807ff-e445-4ccf-ace6-fd913439799b
ms.date: 02/26/2018
ms.keywords: DFDeviceObjectChildListRef_c7ac1028-c3a3-4189-ae63-510bd199fcb2.xml, WdfChildListRetrieveNextDevice, WdfChildListRetrieveNextDevice method, kmdf.wdfchildlistretrievenextdevice, wdf.wdfchildlistretrievenextdevice, wdfchildlist/WdfChildListRetrieveNextDevice
ms.topic: function
f1_keywords:
 - "wdfchildlist/WdfChildListRetrieveNextDevice"
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
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfChildListRetrieveNextDevice
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfChildListRetrieveNextDevice function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfChildListRetrieveNextDevice</b> method traverses a specified child list and retrieves the next child device that matches specified criteria.


## -parameters




### -param ChildList [in]

A handle to a framework child-list object.


### -param Iterator [in]

A pointer to the same caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/ns-wdfchildlist-_wdf_child_list_iterator">WDF_CHILD_LIST_ITERATOR</a> structure that the driver previously supplied to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistbeginiteration">WdfChildListBeginIteration</a>.


### -param Device [out]

A pointer to a location that receives a handle to a framework device object. The received value is <b>NULL</b> if the <i>Iterator</i> parameter specifies the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/ne-wdfchildlist-_wdf_retrieve_child_flags">WdfRetrievePendingChildren</a> flag.


### -param Info [in, out]

A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/ns-wdfchildlist-_wdf_child_retrieve_info">WDF_CHILD_RETRIEVE_INFO</a> structure. This pointer is optional and can be <b>NULL</b>.


## -returns



<b>WdfChildListRetrieveNextDevice</b> returns STATUS_SUCCESS, or another status value for which <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS(status)</a> equals <b>TRUE</b>, if the operation succeeds. Otherwise, this method might return one of the following values:

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
The size of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/ns-wdfchildlist-_wdf_child_list_iterator">WDF_CHILD_LIST_ITERATOR</a> structure that <i>Iterator</i> specified was incorrect

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
The driver has not called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistbeginiteration">WdfChildListBeginIteration</a>.

</td>
</tr>
</table>
 

This method might also return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.



A system bug check occurs if the driver supplies an invalid object handle.





## -remarks



Before calling <b>WdfChildListRetrieveNextDevice</b>, your driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistbeginiteration">WdfChildListBeginIteration</a>. After the driver has finished traversing the child list, it must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistenditeration">WdfChildListEndIteration</a>. The framework then informs the Plug and Play (PnP) manager of any changes that were made to the child list.

Each time the driver calls <b>WdfChildListRetrieveNextDevice</b>, the method retrieves the next child that matches the following search criteria:

<ul>
<li>
The child's type must correspond to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/ne-wdfchildlist-_wdf_retrieve_child_flags">WDF_RETRIEVE_CHILD_FLAGS</a>-typed flags in the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/ns-wdfchildlist-_wdf_child_list_iterator">WDF_CHILD_LIST_ITERATOR</a> structure.

</li>
<li>
If the driver provides a pointer to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_identification_description_compare">EvtChildListIdentificationDescriptionCompare</a> callback function in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/ns-wdfchildlist-_wdf_child_retrieve_info">WDF_CHILD_RETRIEVE_INFO</a> structure, the callback function must return <b>TRUE</b>.

</li>
</ul>
If the driver provides an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_identification_description_compare">EvtChildListIdentificationDescriptionCompare</a> callback function, it must also provide an <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">identification description</a> in the WDF_CHILD_RETRIEVE_INFO structure. The framework uses the callback function to compare the passed-in identification descriptor with a child's description in the child list, if the WDF_RETRIEVE_CHILD_FLAGS-typed flags indicate that the child is a match candidate. If the callback function returns <b>TRUE</b>, the match is successful. If the callback function returns <b>FALSE</b>, the framework looks for another candidate.

When <b>WdfChildListRetrieveNextDevice</b> finds a match, it copies the child's identification description and address description into the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/ns-wdfchildlist-_wdf_child_retrieve_info">WDF_CHILD_RETRIEVE_INFO</a> structure, if the pointer that the <i>Info</i> parameter specifies is not <b>NULL</b>. (Note that this operation overwrites the driver's input identification description.) The method also places a handle to the child's device object in the location that the <i>Device</i> parameter identifies.

For more information about child lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.


#### Examples

The following code example informs the framework that all of a parent device's children are being ejected. The example obtains a device's default child list and walks through the list. It obtains each child's identification descriptor, and it passes each identification descriptor to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistrequestchildeject">WdfChildListRequestChildEject</a>.

```cpp
WDF_CHILD_LIST_ITERATOR  iterator;
WDFDEVICE  hChild;
NTSTATUS  status = STATUS_INVALID_PARAMETER;
WDFCHILDLIST  list;
WDF_CHILD_RETRIEVE_INFO  childInfo;
PDO_IDENTIFICATION_DESCRIPTION  description;
BOOLEAN  ret;

list = WdfFdoGetDefaultChildList(Device);

WDF_CHILD_LIST_ITERATOR_INIT(
                             &iterator,
                             WdfRetrievePresentChildren
                             );
WdfChildListBeginIteration(
                           list,
                           &iterator
                           );
for (;;) {
    WDF_CHILD_RETRIEVE_INFO_INIT(
                                 &childInfo,
                                 &description.Header
                                 );
    WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT(
                                                     &description.Header,
                                                     sizeof(description)
                                                     );
    status = WdfChildListRetrieveNextDevice(
                                            list, 
                                            &iterator, 
                                            &hChild, 
                                            &childInfo
                                            );
    if (!NT_SUCCESS(status) || status == STATUS_NO_MORE_ENTRIES) {
       break;
    }
    ASSERT(childInfo.Status == WdfChildListRetrieveDeviceSuccess);

    ret = WdfChildListRequestChildEject(
                                        list,
                                        &description.Header
                                        );
    if(!ret) {
       WDFVERIFY(ret);
    }
}
WdfChildListEndIteration(
                         list,
                         &iterator
                         );
if (status == STATUS_NO_MORE_ENTRIES) {
   status = STATUS_SUCCESS;
}
return status;
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_identification_description_compare">EvtChildListIdentificationDescriptionCompare</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdf_child_identification_description_header_init">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/ns-wdfchildlist-_wdf_child_list_iterator">WDF_CHILD_LIST_ITERATOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdf_child_list_iterator_init">WDF_CHILD_LIST_ITERATOR_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/ns-wdfchildlist-_wdf_child_retrieve_info">WDF_CHILD_RETRIEVE_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/ne-wdfchildlist-_wdf_retrieve_child_flags">WDF_RETRIEVE_CHILD_FLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistbeginiteration">WdfChildListBeginIteration</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistbeginscan">WdfChildListBeginScan</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistenditeration">WdfChildListEndIteration</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistrequestchildeject">WdfChildListRequestChildEject</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfchildlist/nf-wdfchildlist-wdfchildlistretrievenextdevice">WdfChildListRetrieveNextDevice</a>
 

 

