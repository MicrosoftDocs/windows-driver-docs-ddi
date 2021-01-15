---
UID: NS:wdfchildlist._WDF_CHILD_RETRIEVE_INFO
title: _WDF_CHILD_RETRIEVE_INFO (wdfchildlist.h)
description: The WDF_CHILD_RETRIEVE_INFO structure contains information about a child device that is obtained by calling WdfChildListRetrieveNextDevice or WdfChildListRetrievePdo.
old-location: wdf\wdf_child_retrieve_info.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WDF_CHILD_RETRIEVE_INFO structure"]
ms.keywords: "*PWDF_CHILD_RETRIEVE_INFO, DFDeviceObjectChildListRef_f2075d85-7f9e-4b9c-b702-c2ef2be65987.xml, PWDF_CHILD_RETRIEVE_INFO, PWDF_CHILD_RETRIEVE_INFO structure pointer, WDF_CHILD_RETRIEVE_INFO, WDF_CHILD_RETRIEVE_INFO structure, _WDF_CHILD_RETRIEVE_INFO, kmdf.wdf_child_retrieve_info, wdf.wdf_child_retrieve_info, wdfchildlist/PWDF_CHILD_RETRIEVE_INFO, wdfchildlist/WDF_CHILD_RETRIEVE_INFO"
req.header: wdfchildlist.h
req.include-header: Wdf.h
req.target-type: Windows
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
req.irql: 
targetos: Windows
req.typenames: WDF_CHILD_RETRIEVE_INFO, *PWDF_CHILD_RETRIEVE_INFO
f1_keywords:
 - _WDF_CHILD_RETRIEVE_INFO
 - wdfchildlist/_WDF_CHILD_RETRIEVE_INFO
 - PWDF_CHILD_RETRIEVE_INFO
 - wdfchildlist/PWDF_CHILD_RETRIEVE_INFO
 - WDF_CHILD_RETRIEVE_INFO
 - wdfchildlist/WDF_CHILD_RETRIEVE_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wdfchildlist.h
api_name:
 - _WDF_CHILD_RETRIEVE_INFO
 - PWDF_CHILD_RETRIEVE_INFO
 - WDF_CHILD_RETRIEVE_INFO
---

# _WDF_CHILD_RETRIEVE_INFO structure


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

The WDF_CHILD_RETRIEVE_INFO structure contains information about a child device that is obtained by calling <a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistretrievenextdevice">WdfChildListRetrieveNextDevice</a> or <a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistretrievepdo">WdfChildListRetrievePdo</a>.

## -struct-fields

### -field Size

The size, in bytes, of this structure.

### -field IdentificationDescription

A pointer to a driver-allocated <a href="/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a> structure. The driver must supply a value for this structure's <b>IdentificationDescriptionSize</b> member. 

If the driver is calling <a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistretrievenextdevice">WdfChildListRetrieveNextDevice</a> and supplying an <a href="/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_identification_description_compare">EvtChildListIdentificationDescriptionCompare</a> callback function, the driver must also provide an <a href="/windows-hardware/drivers/wdf/dynamic-enumeration">identification description</a> that the callback function can use to compare with an entry in a child list.

If the driver is calling <a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistretrievepdo">WdfChildListRetrievePdo</a>, the driver must fill in the entire identification description.

### -field AddressDescription

A pointer to a driver-allocated <a href="/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_address_description_header">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a> structure. The driver must supply a value for this structure's <b>AddressDescriptionSize</b> member. The framework fills in the rest of the <a href="/windows-hardware/drivers/wdf/dynamic-enumeration">address description</a> when it retrieves a child from the child list. If the value of <b>AddressDescriptionSize</b> is <b>NULL</b>, address description information is not retrieved.

### -field Status

A <a href="/windows-hardware/drivers/ddi/wdfchildlist/ne-wdfchildlist-_wdf_child_list_retrieve_device_status">WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS</a>-typed value that the framework provides.

### -field EvtChildListIdentificationDescriptionCompare

A driver-supplied pointer to an <a href="/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_identification_description_compare">EvtChildListIdentificationDescriptionCompare</a> callback function. 

If the driver is calling <a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistretrievenextdevice">WdfChildListRetrieveNextDevice</a>, this pointer is optional and can be <b>NULL</b>. 

If the driver is calling <a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistretrievepdo">WdfChildListRetrievePdo</a>, this pointer is not used.

## -remarks

The WDF_CHILD_RETRIEVE_INFO structure is passed to the <a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistretrievenextdevice">WdfChildListRetrieveNextDevice</a> and <a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistretrievepdo">WdfChildListRetrievePdo</a> methods. 

To initialize a WDF_CHILD_RETRIEVE_INFO structure, the driver must call <a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdf_child_retrieve_info_init">WDF_CHILD_RETRIEVE_INFO_INIT</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_identification_description_compare">EvtChildListIdentificationDescriptionCompare</a>



<a href="/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_address_description_header">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a>



<a href="/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>



<a href="/windows-hardware/drivers/ddi/wdfchildlist/ne-wdfchildlist-_wdf_child_list_retrieve_device_status">WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS</a>



<a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistretrievenextdevice">WdfChildListRetrieveNextDevice</a>



<a href="/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistretrievepdo">WdfChildListRetrievePdo</a>

