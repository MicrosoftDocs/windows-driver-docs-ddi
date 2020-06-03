---
UID: NC:wdfchildlist.EVT_WDF_CHILD_LIST_ADDRESS_DESCRIPTION_DUPLICATE
title: EVT_WDF_CHILD_LIST_ADDRESS_DESCRIPTION_DUPLICATE (wdfchildlist.h)
description: A driver's EvtChildListAddressDescriptionDuplicate event callback function duplicates a child address description.
old-location: wdf\evtchildlistaddressdescriptionduplicate.htm
tech.root: wdf
ms.assetid: 3b99401c-5a36-4ccd-b3a4-c5687310c29b
ms.date: 02/26/2018
keywords: ["EVT_WDF_CHILD_LIST_ADDRESS_DESCRIPTION_DUPLICATE callback function"]
ms.keywords: DFDeviceObjectChildListRef_5ade5582-8a35-49cb-a291-e6d972822138.xml, EVT_WDF_CHILD_LIST_ADDRESS_DESCRIPTION_DUPLICATE, EVT_WDF_CHILD_LIST_ADDRESS_DESCRIPTION_DUPLICATE callback, EvtChildListAddressDescriptionDuplicate, EvtChildListAddressDescriptionDuplicate callback function, kmdf.evtchildlistaddressdescriptionduplicate, wdf.evtchildlistaddressdescriptionduplicate, wdfchildlist/EvtChildListAddressDescriptionDuplicate
f1_keywords:
 - "wdfchildlist/EvtChildListAddressDescriptionDuplicate"
req.header: wdfchildlist.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- WdfChildlist.h
api_name:
- EvtChildListAddressDescriptionDuplicate
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_WDF_CHILD_LIST_ADDRESS_DESCRIPTION_DUPLICATE callback function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtChildListAddressDescriptionDuplicate</i> event callback function duplicates a child address description.


## -parameters




### -param ChildList [in]

A handle to a framework child-list object.


### -param SourceAddressDescription [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_address_description_header">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a> structure that identifies the source location of the child address description.


### -param DestinationAddressDescription [out]

A pointer to a WDF_CHILD_ADDRESS_DESCRIPTION_HEADER structure that identifies the destination location of the child address description.


## -returns



The <i>EvtChildListAddressDescriptionDuplicate</i> callback function must return STATUS_SUCCESS, or another status value for which <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/using-ntstatus-values">NT_SUCCESS</a>(<i>status</i>) equals <b>TRUE</b>, if the operation succeeds. Otherwise, this function must return a status value for which NT_SUCCESS(<i>status</i>) equals <b>FALSE</b>. 




## -remarks



If a bus driver is using <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">dynamic enumeration</a>, it can register an <i>EvtChildListAddressDescriptionDuplicate</i> callback function by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitsetdefaultchildlistconfig">WdfFdoInitSetDefaultChildListConfig</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistcreate">WdfChildListCreate</a>.

The framework duplicates driver-supplied address descriptions so that it can have internal copies of the descriptions.

The <i>EvtChildListAddressDescriptionDuplicate</i> callback function must create a duplicate copy of an address description. A driver must supply this callback function if its child devices require an address description, and if the framework cannot call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlcopymemory">RtlCopyMemory</a> to duplicate the address description. (The framework cannot call <b>RtlCopyMemory</b> if the description contains pointers to additional memory.)

If your driver provides address descriptions but does not provide a <i>EvtChildListAddressDescriptionDuplicate</i> callback function, the framework duplicates address descriptions by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlcopymemory">RtlCopyMemory</a>.

The following steps describe a typical scenario:

<ol>
<li>
The driver determines that a child device exists.

</li>
<li>
The driver creates an address description by filling in a driver-defined structure that contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_address_description_header">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a> structure and possibly by dynamically allocating additional memory to store address information that has a device-specific size. 

</li>
<li>
The driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistaddorupdatechilddescriptionaspresent">WdfChildListAddOrUpdateChildDescriptionAsPresent</a> to report a child device, supplying a pointer to the address description. 

</li>
<li>
The framework calls the <i>EvtChildListAddressDescriptionDuplicate</i> callback function (if it exists) or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlcopymemory">RtlCopyMemory</a> to duplicate the address description so that it can have an internal copy of the description.

</li>
</ol>
The framework can use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlcopymemory">RtlCopyMemory</a> to duplicate an address description, if the description consists of a single structure with a predetermined size that is specified by the <b>AddressDescriptionSize</b> member of the WDF_CHILD_ADDRESS_DESCRIPTION_HEADER structure. However, sometimes the description must also contain additional information that is stored in dynamically allocated memory. In this case, you will typically define a description structure so that a member points to the dynamically allocated memory, and your driver must provide an <i>EvtChildListAddressDescriptionDuplicate</i> callback function. The callback function must do the following:

<ol>
<li>
Allocate additional memory, typically by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepool">ExAllocatePool</a>.

</li>
<li>
Store the allocated memory's address in the driver-defined address description structure (that is, the callback function's <i>DestinationAddressDescription</i> structure).

</li>
<li>
Copy other structure members from the callback function's <i>SourceAddressDescription</i> structure to the callback function's <i>DestinationAddressDescription</i> structure.

</li>
</ol>
The only <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/">framework child-list object method</a> that a driver's <i>EvtChildListAddressDescriptionDuplicate</i> callback function can call is <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistgetdevice">WdfChildListGetDevice</a>.

The framework acquires an internal child-list object lock before calling the <i>EvtChildListAddressDescriptionDuplicate</i> callback function. The callback function must only perform operations that are related to the described duplication operation, such as calling framework memory object methods and accessing object context space. It must not call methods that access other drivers.

If your driver supplies an <i>EvtChildListAddressDescriptionDuplicate</i> callback function, it might also need <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_address_description_copy">EvtChildListAddressDescriptionCopy</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_address_description_cleanup">EvtChildListAddressDescriptionCleanup</a> callback functions.

For more information about dynamic enumeration, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/enumerating-the-devices-on-a-bus">Enumerating the Devices on a Bus</a><u>.</u>





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_address_description_cleanup">EvtChildListAddressDescriptionCleanup</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepool">ExAllocatePool</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlcopymemory">RtlCopyMemory</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_address_description_header">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistaddorupdatechilddescriptionaspresent">WdfChildListAddOrUpdateChildDescriptionAsPresent</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistcreate">WdfChildListCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistgetdevice">WdfChildListGetDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitsetdefaultchildlistconfig">WdfFdoInitSetDefaultChildListConfig</a>
 

 

