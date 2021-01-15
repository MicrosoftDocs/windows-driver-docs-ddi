---
UID: NC:wdfchildlist.EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COPY
title: EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COPY (wdfchildlist.h)
description: A driver's EvtChildListIdentificationDescriptionCopy event callback function copies a child identification description from one specified location to another.
old-location: wdf\evtchildlistidentificationdescriptioncopy.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COPY callback function"]
ms.keywords: DFDeviceObjectChildListRef_8568b87d-544a-4574-a9c7-c5498a30a758.xml, EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COPY, EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COPY callback, EvtChildListIdentificationDescriptionCopy, EvtChildListIdentificationDescriptionCopy callback function, kmdf.evtchildlistidentificationdescriptioncopy, wdf.evtchildlistidentificationdescriptioncopy, wdfchildlist/EvtChildListIdentificationDescriptionCopy
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
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COPY
 - wdfchildlist/EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COPY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - WdfChildlist.h
api_name:
 - EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COPY
---

# EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COPY callback function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtChildListIdentificationDescriptionCopy</i> event callback function copies a child identification description from one specified location to another.

## -parameters

### -param ChildList 

[in]
A handle to a framework child-list object.

### -param SourceIdentificationDescription 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure that identifies the source location of the child identification description.

### -param DestinationIdentificationDescription 

[out]
A pointer to a <a href="/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure that identifies the destination location of the child identification description.

## -remarks

If a bus driver is using <a href="/windows-hardware/drivers/wdf/dynamic-enumeration">dynamic enumeration</a>, it can register an <i>EvtChildListIdentificationDescriptionCopy</i> callback function by calling <a href="/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitsetdefaultchildlistconfig">WdfFdoInitSetDefaultChildListConfig</a> or <a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistcreate">WdfChildListCreate</a>.

The framework copies information from one driver-supplied identification description to another when it needs to update an existing description with new information, or when it needs to pass the contents of an identification description to the driver.

The <i>EvtChildListIdentificationDescriptionCopy</i> callback function must copy the contents of a source description to a destination description. A driver must supply this callback function if the framework cannot call <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlcopymemory">RtlCopyMemory</a> to copy the identification description. (The framework cannot call <b>RtlCopyMemory</b> if the description contains pointers to additional memory.)

If your driver does not provide an <i>EvtChildListIdentificationDescriptionCopy</i> callback function, the framework copies identification descriptions by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlcopymemory">RtlCopyMemory</a>.

The following steps describe a possible scenario:

<ol>
<li>
The driver that is traversing a child list calls <a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistretrievenextdevice">WdfChildListRetrieveNextDevice</a>. The driver supplies a <a href="/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_retrieve_info">WDF_CHILD_RETRIEVE_INFO</a> structure so that it can receive the child device's identification description.

</li>
<li>
The framework calls the <i>EvtChildListIdentificationDescriptionCopy</i> callback function (if it exists) or <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlcopymemory">RtlCopyMemory</a> to copy the device's identification description. The source of the copy operation is the framework's internal copy of the description. The destination is memory that the driver allocated and identified in its WDF_CHILD_RETRIEVE_INFO structure.

</li>
</ol>
The framework can use <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlcopymemory">RtlCopyMemory</a> to copy an identification description, if the description consists of a single structure with a predetermined size that is specified by the <b>IdentificationDescriptionSize</b> member of the <a href="/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure. However, sometimes the description must also contain additional information that is stored in dynamically allocated memory. In this case, you will typically define a description structure so that a member points to the dynamically allocated memory, and your driver must provide an <i>EvtChildListIdentificationDescriptionCopy</i> callback function. The callback function must do the following:

<ol>
<li>
In the callback function's <i>SourceIdentificationDescription</i> and <i>DestinationIdentificationDescription</i> structures, find the pointers to dynamically allocated memory.

</li>
<li>
Copy the dynamically allocated memory from the source to the destination, using the pointers.

</li>
<li>
Copy other structure members from the callback function's <i>SourceIdentificationDescription</i> structure to the callback function's <i>DestinationIdentificationDescription</i> structure.

</li>
</ol>
The only <a href="/windows-hardware/drivers/ddi/wdfchildlist/">framework child-list object method</a> that a driver's <i>EvtChildListIdentificationDescriptionCopy</i> callback function can call is <a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistgetdevice">WdfChildListGetDevice</a>.

The framework acquires an internal child-list object lock before calling the <i>EvtChildListIdentificationDescriptionCopy</i> callback function. The callback function must only perform operations that are related to the copy operation, such as calling framework memory object methods and accessing object context space. It must not call methods that access other drivers.

If your driver supplies an <i>EvtChildListIdentificationDescriptionCopy</i> callback function, it might also need <a href="/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_identification_description_duplicate">EvtChildListIdentificationDescriptionDuplicate</a>, <a href="/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_identification_description_compare">EvtChildListIdentificationDescriptionCompare</a>, and <a href="/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_identification_description_cleanup">EvtChildListIdentificationDescriptionCleanup</a> callback functions.

For more information about dynamic enumeration, see <a href="/windows-hardware/drivers/wdf/enumerating-the-devices-on-a-bus">Enumerating the Devices on a Bus</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_identification_description_cleanup">EvtChildListIdentificationDescriptionCleanup</a>



<a href="/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_identification_description_compare">EvtChildListIdentificationDescriptionCompare</a>



<a href="/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_identification_description_duplicate">EvtChildListIdentificationDescriptionDuplicate</a>



<a href="/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>



<a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistcreate">WdfChildListCreate</a>



<a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistgetdevice">WdfChildListGetDevice</a>



<a href="/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitsetdefaultchildlistconfig">WdfFdoInitSetDefaultChildListConfig</a>

