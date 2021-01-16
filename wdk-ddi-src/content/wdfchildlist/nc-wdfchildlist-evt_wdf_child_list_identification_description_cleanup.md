---
UID: NC:wdfchildlist.EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_CLEANUP
title: EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_CLEANUP (wdfchildlist.h)
description: A driver's EvtChildListIdentificationDescriptionCleanup event callback function frees any memory allocations for an identification description that the driver's EvtChildListIdentificationDescriptionDuplicate callback function allocated.
old-location: wdf\evtchildlistidentificationdescriptioncleanup.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_CLEANUP callback function"]
ms.keywords: DFDeviceObjectChildListRef_f70d9bc7-a6f9-41c4-a6c3-7a9ef413096c.xml, EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_CLEANUP, EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_CLEANUP callback, EvtChildListIdentificationDescriptionCleanup, EvtChildListIdentificationDescriptionCleanup callback function, kmdf.evtchildlistidentificationdescriptioncleanup, wdf.evtchildlistidentificationdescriptioncleanup, wdfchildlist/EvtChildListIdentificationDescriptionCleanup
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
 - EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_CLEANUP
 - wdfchildlist/EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_CLEANUP
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - WdfChildlist.h
api_name:
 - EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_CLEANUP
---

# EVT_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_CLEANUP callback function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtChildListIdentificationDescriptionCleanup</i> event callback function frees any memory allocations for an identification description that the driver's <a href="/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_identification_description_duplicate">EvtChildListIdentificationDescriptionDuplicate</a> callback function allocated.

## -parameters

### -param ChildList 

[in]
A handle to a framework child-list object.

### -param IdentificationDescription 

[in, out]
A pointer to a <a href="/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure that identifies an identification description.

## -remarks

If a bus driver is using <a href="/windows-hardware/drivers/wdf/dynamic-enumeration">dynamic enumeration</a>, it can register an <i>EvtChildListIdentificationDescriptionCleanup</i> callback function by calling <a href="/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitsetdefaultchildlistconfig">WdfFdoInitSetDefaultChildListConfig</a> or <a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistcreate">WdfChildListCreate</a>.

If an identification description points to additional information that is stored in dynamically allocated memory, and if that memory is allocated by an <a href="/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_identification_description_duplicate">EvtChildListIdentificationDescriptionDuplicate</a> callback function, the driver must provide an <i>EvtChildListIdentificationDescriptionCleanup</i> callback function. 

Typically, the <a href="/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_identification_description_duplicate">EvtChildListIdentificationDescriptionDuplicate</a> callback function allocates memory by calling <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepool">ExAllocatePool</a>. The <i>EvtChildListIdentificationDescriptionCleanup</i> callback function must deallocate that memory by calling <a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool">ExFreePool</a>. This callback function must not attempt to deallocate the rest of the identification description. In other words, the callback function must not deallocate the address description structure that the <i>IdentificationDescription</i> parameter points to; it must deallocate only additional memory allocations that the description structure points to.

For more information about dynamic enumeration, see <a href="/windows-hardware/drivers/wdf/enumerating-the-devices-on-a-bus">Enumerating the Devices on a Bus</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_identification_description_duplicate">EvtChildListIdentificationDescriptionDuplicate</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepool">ExAllocatePool</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool">ExFreePool</a>



<a href="/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>



<a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistcreate">WdfChildListCreate</a>



<a href="/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitsetdefaultchildlistconfig">WdfFdoInitSetDefaultChildListConfig</a>

