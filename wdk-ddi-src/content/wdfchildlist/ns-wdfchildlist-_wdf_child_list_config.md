---
UID: NS:wdfchildlist._WDF_CHILD_LIST_CONFIG
title: _WDF_CHILD_LIST_CONFIG (wdfchildlist.h)
description: The WDF_CHILD_LIST_CONFIG structure contains configuration information for a list of child devices.
old-location: wdf\wdf_child_list_config.htm
tech.root: wdf
ms.assetid: d0a392f4-c7c3-4b61-960c-b94f9605f5a4
ms.date: 02/26/2018
keywords: ["_WDF_CHILD_LIST_CONFIG structure"]
ms.keywords: "*PWDF_CHILD_LIST_CONFIG, DFDeviceObjectChildListRef_9666f463-1673-4208-9745-e1d12b523569.xml, PWDF_CHILD_LIST_CONFIG, PWDF_CHILD_LIST_CONFIG structure pointer, WDF_CHILD_LIST_CONFIG, WDF_CHILD_LIST_CONFIG structure, _WDF_CHILD_LIST_CONFIG, kmdf.wdf_child_list_config, wdf.wdf_child_list_config, wdfchildlist/PWDF_CHILD_LIST_CONFIG, wdfchildlist/WDF_CHILD_LIST_CONFIG"
f1_keywords:
 - "wdfchildlist/WDF_CHILD_LIST_CONFIG"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wdfchildlist.h
api_name:
- WDF_CHILD_LIST_CONFIG
product:
- Windows
targetos: Windows
req.typenames: WDF_CHILD_LIST_CONFIG, *PWDF_CHILD_LIST_CONFIG
---

# _WDF_CHILD_LIST_CONFIG structure


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_CHILD_LIST_CONFIG</b> structure contains configuration information for a list of child devices. 


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field IdentificationDescriptionSize

The size, in bytes, of each child's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">identification description</a>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>.


### -field AddressDescriptionSize

The size, in bytes, of each child's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">address description</a>. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_address_description_header">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a>.


### -field EvtChildListCreateDevice

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_create_device">EvtChildListCreateDevice</a> event callback function. This callback function is required.


### -field EvtChildListScanForChildren

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_scan_for_children">EvtChildListScanForChildren</a> event callback function. This callback function is optional.


### -field EvtChildListIdentificationDescriptionCopy

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_identification_description_copy">EvtChildListIdentificationDescriptionCopy</a> event callback function. This callback function is optional.


### -field EvtChildListIdentificationDescriptionDuplicate

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_identification_description_duplicate">EvtChildListIdentificationDescriptionDuplicate</a> event callback function. This callback function is optional.


### -field EvtChildListIdentificationDescriptionCleanup

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_identification_description_cleanup">EvtChildListIdentificationDescriptionCleanup</a> event callback function. This callback function is optional.


### -field EvtChildListIdentificationDescriptionCompare

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_identification_description_compare">EvtChildListIdentificationDescriptionCompare</a> event callback function. This callback function is optional.


### -field EvtChildListAddressDescriptionCopy

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_address_description_copy">EvtChildListAddressDescriptionCopy</a> event callback function. This callback function is optional.


### -field EvtChildListAddressDescriptionDuplicate

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_address_description_duplicate">EvtChildListAddressDescriptionDuplicate</a> event callback function. This callback function is optional.


### -field EvtChildListAddressDescriptionCleanup

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_address_description_cleanup">EvtChildListAddressDescriptionCleanup</a> event callback function. This callback function is optional.


### -field EvtChildListDeviceReenumerated

A pointer to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_device_reenumerated">EvtChildListDeviceReenumerated</a> event callback function. This callback function is optional.


## -remarks



The <b>WDF_CHILD_LIST_CONFIG</b> structure is used as input to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitsetdefaultchildlistconfig">WdfFdoInitSetDefaultChildListConfig</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistcreate">WdfChildListCreate</a> methods.

To initialize a WDF_CHILD_LIST_CONFIG structure, the driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdf_child_list_config_init">WDF_CHILD_LIST_CONFIG_INIT</a>.

For more information about child lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_address_description_header">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_identification_description_header">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdf_child_list_config_init">WDF_CHILD_LIST_CONFIG_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistcreate">WdfChildListCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitsetdefaultchildlistconfig">WdfFdoInitSetDefaultChildListConfig</a>
 

 

