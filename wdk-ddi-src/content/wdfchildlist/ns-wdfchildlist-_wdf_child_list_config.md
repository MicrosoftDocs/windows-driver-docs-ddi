---
UID: NS:wdfchildlist._WDF_CHILD_LIST_CONFIG
title: "_WDF_CHILD_LIST_CONFIG"
author: windows-driver-content
description: The WDF_CHILD_LIST_CONFIG structure contains configuration information for a list of child devices.
old-location: wdf\wdf_child_list_config.htm
old-project: wdf
ms.assetid: d0a392f4-c7c3-4b61-960c-b94f9605f5a4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWDF_CHILD_LIST_CONFIG, DFDeviceObjectChildListRef_9666f463-1673-4208-9745-e1d12b523569.xml, PWDF_CHILD_LIST_CONFIG, PWDF_CHILD_LIST_CONFIG structure pointer, WDF_CHILD_LIST_CONFIG, WDF_CHILD_LIST_CONFIG structure, _WDF_CHILD_LIST_CONFIG, kmdf.wdf_child_list_config, wdf.wdf_child_list_config, wdfchildlist/PWDF_CHILD_LIST_CONFIG, wdfchildlist/WDF_CHILD_LIST_CONFIG"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfchildlist.h
api_name:
-	WDF_CHILD_LIST_CONFIG
product: Windows
targetos: Windows
req.typenames: WDF_CHILD_LIST_CONFIG, *PWDF_CHILD_LIST_CONFIG
req.product: Windows 10 or later.
---

# _WDF_CHILD_LIST_CONFIG structure


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_CHILD_LIST_CONFIG</b> structure contains configuration information for a list of child devices. 


## -syntax


````
typedef struct _WDF_CHILD_LIST_CONFIG {
  ULONG                                                   Size;
  ULONG                                                   IdentificationDescriptionSize;
  ULONG                                                   AddressDescriptionSize;
  PFN_WDF_CHILD_LIST_CREATE_DEVICE                        EvtChildListCreateDevice;
  PFN_WDF_CHILD_LIST_SCAN_FOR_CHILDREN                    EvtChildListScanForChildren;
  PFN_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COPY      EvtChildListIdentificationDescriptionCopy;
  PFN_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_DUPLICATE EvtChildListIdentificationDescriptionDuplicate;
  PFN_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_CLEANUP   EvtChildListIdentificationDescriptionCleanup;
  PFN_WDF_CHILD_LIST_IDENTIFICATION_DESCRIPTION_COMPARE   EvtChildListIdentificationDescriptionCompare;
  PFN_WDF_CHILD_LIST_ADDRESS_DESCRIPTION_COPY             EvtChildListAddressDescriptionCopy;
  PFN_WDF_CHILD_LIST_ADDRESS_DESCRIPTION_DUPLICATE        EvtChildListAddressDescriptionDuplicate;
  PFN_WDF_CHILD_LIST_ADDRESS_DESCRIPTION_CLEANUP          EvtChildListAddressDescriptionCleanup;
  PFN_WDF_CHILD_LIST_DEVICE_REENUMERATED                  EvtChildListDeviceReenumerated;
} WDF_CHILD_LIST_CONFIG, *PWDF_CHILD_LIST_CONFIG;
````


## -struct-fields




### -field Size

The size, in bytes, of this structure.


### -field IdentificationDescriptionSize

The size, in bytes, of each child's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">identification description</a>. For more information, see <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_identification_description_header.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>.


### -field AddressDescriptionSize

The size, in bytes, of each child's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">address description</a>. For more information, see <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_address_description_header.md">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a>.


### -field EvtChildListCreateDevice

A pointer to the driver's <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_create_device.md">EvtChildListCreateDevice</a> event callback function. This callback function is required.


### -field EvtChildListScanForChildren

A pointer to the driver's <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_scan_for_children.md">EvtChildListScanForChildren</a> event callback function. This callback function is optional.


### -field EvtChildListIdentificationDescriptionCopy

A pointer to the driver's <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_copy.md">EvtChildListIdentificationDescriptionCopy</a> event callback function. This callback function is optional.


### -field EvtChildListIdentificationDescriptionDuplicate

A pointer to the driver's <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_duplicate.md">EvtChildListIdentificationDescriptionDuplicate</a> event callback function. This callback function is optional.


### -field EvtChildListIdentificationDescriptionCleanup

A pointer to the driver's <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_cleanup.md">EvtChildListIdentificationDescriptionCleanup</a> event callback function. This callback function is optional.


### -field EvtChildListIdentificationDescriptionCompare

A pointer to the driver's <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_identification_description_compare.md">EvtChildListIdentificationDescriptionCompare</a> event callback function. This callback function is optional.


### -field EvtChildListAddressDescriptionCopy

A pointer to the driver's <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_address_description_copy.md">EvtChildListAddressDescriptionCopy</a> event callback function. This callback function is optional.


### -field EvtChildListAddressDescriptionDuplicate

A pointer to the driver's <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_address_description_duplicate.md">EvtChildListAddressDescriptionDuplicate</a> event callback function. This callback function is optional.


### -field EvtChildListAddressDescriptionCleanup

A pointer to the driver's <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_address_description_cleanup.md">EvtChildListAddressDescriptionCleanup</a> event callback function. This callback function is optional.


### -field EvtChildListDeviceReenumerated

A pointer to the driver's <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_device_reenumerated.md">EvtChildListDeviceReenumerated</a> event callback function. This callback function is optional.


## -remarks



The <b>WDF_CHILD_LIST_CONFIG</b> structure is used as input to the <a href="..\wdffdo\nf-wdffdo-wdffdoinitsetdefaultchildlistconfig.md">WdfFdoInitSetDefaultChildListConfig</a> and <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistcreate.md">WdfChildListCreate</a> methods.

To initialize a WDF_CHILD_LIST_CONFIG structure, the driver must call <a href="..\wdfchildlist\nf-wdfchildlist-wdf_child_list_config_init.md">WDF_CHILD_LIST_CONFIG_INIT</a>.

For more information about child lists, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.




## -see-also

<a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_identification_description_header.md">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>



<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistcreate.md">WdfChildListCreate</a>



<a href="..\wdffdo\nf-wdffdo-wdffdoinitsetdefaultchildlistconfig.md">WdfFdoInitSetDefaultChildListConfig</a>



<a href="..\wdfchildlist\nf-wdfchildlist-wdf_child_list_config_init.md">WDF_CHILD_LIST_CONFIG_INIT</a>



<a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_address_description_header.md">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_CHILD_LIST_CONFIG structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

