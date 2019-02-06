---
UID: NS:wdfchildlist._WDF_CHILD_LIST_CONFIG
title: _WDF_CHILD_LIST_CONFIG (wdfchildlist.h)
description: The WDF_CHILD_LIST_CONFIG structure contains configuration information for a list of child devices.
old-location: wdf\wdf_child_list_config.htm
tech.root: wdf
ms.assetid: d0a392f4-c7c3-4b61-960c-b94f9605f5a4
ms.date: 02/26/2018
ms.keywords: "*PWDF_CHILD_LIST_CONFIG, DFDeviceObjectChildListRef_9666f463-1673-4208-9745-e1d12b523569.xml, PWDF_CHILD_LIST_CONFIG, PWDF_CHILD_LIST_CONFIG structure pointer, WDF_CHILD_LIST_CONFIG, WDF_CHILD_LIST_CONFIG structure, _WDF_CHILD_LIST_CONFIG, kmdf.wdf_child_list_config, wdf.wdf_child_list_config, wdfchildlist/PWDF_CHILD_LIST_CONFIG, wdfchildlist/WDF_CHILD_LIST_CONFIG"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdfchildlist.h
api_name:
-	WDF_CHILD_LIST_CONFIG
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

The size, in bytes, of each child's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">identification description</a>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff551223">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>.


### -field AddressDescriptionSize

The size, in bytes, of each child's <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">address description</a>. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff551219">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a>.


### -field EvtChildListCreateDevice

A pointer to the driver's <a href="https://msdn.microsoft.com/296fbe06-1680-43a8-b5c3-1a1faa19c6c3">EvtChildListCreateDevice</a> event callback function. This callback function is required.


### -field EvtChildListScanForChildren

A pointer to the driver's <a href="https://msdn.microsoft.com/57b06ecd-fc8c-4653-bb78-2bc6ecde6d63">EvtChildListScanForChildren</a> event callback function. This callback function is optional.


### -field EvtChildListIdentificationDescriptionCopy

A pointer to the driver's <a href="https://msdn.microsoft.com/c44d6a2f-c7ef-486d-973e-aada068ddc06">EvtChildListIdentificationDescriptionCopy</a> event callback function. This callback function is optional.


### -field EvtChildListIdentificationDescriptionDuplicate

A pointer to the driver's <a href="https://msdn.microsoft.com/5c2ec27c-2d88-4e0c-8f11-4f58d720df46">EvtChildListIdentificationDescriptionDuplicate</a> event callback function. This callback function is optional.


### -field EvtChildListIdentificationDescriptionCleanup

A pointer to the driver's <a href="https://msdn.microsoft.com/4874f03e-b4e7-4fae-8737-7630462cd7e5">EvtChildListIdentificationDescriptionCleanup</a> event callback function. This callback function is optional.


### -field EvtChildListIdentificationDescriptionCompare

A pointer to the driver's <a href="https://msdn.microsoft.com/b807f9f8-588f-4303-be97-a9fd4cff2bbd">EvtChildListIdentificationDescriptionCompare</a> event callback function. This callback function is optional.


### -field EvtChildListAddressDescriptionCopy

A pointer to the driver's <a href="https://msdn.microsoft.com/b73ec39c-8d93-4992-8791-5070a088701a">EvtChildListAddressDescriptionCopy</a> event callback function. This callback function is optional.


### -field EvtChildListAddressDescriptionDuplicate

A pointer to the driver's <a href="https://msdn.microsoft.com/3b99401c-5a36-4ccd-b3a4-c5687310c29b">EvtChildListAddressDescriptionDuplicate</a> event callback function. This callback function is optional.


### -field EvtChildListAddressDescriptionCleanup

A pointer to the driver's <a href="https://msdn.microsoft.com/845c8c96-7d34-4273-963e-b7f644884f26">EvtChildListAddressDescriptionCleanup</a> event callback function. This callback function is optional.


### -field EvtChildListDeviceReenumerated

A pointer to the driver's <a href="https://msdn.microsoft.com/404436c3-6ddb-4212-ad51-23a956d7df52">EvtChildListDeviceReenumerated</a> event callback function. This callback function is optional.


## -remarks



The <b>WDF_CHILD_LIST_CONFIG</b> structure is used as input to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547258">WdfFdoInitSetDefaultChildListConfig</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff545615">WdfChildListCreate</a> methods.

To initialize a WDF_CHILD_LIST_CONFIG structure, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff551228">WDF_CHILD_LIST_CONFIG_INIT</a>.

For more information about child lists, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">Dynamic Enumeration</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551219">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551223">WDF_CHILD_IDENTIFICATION_DESCRIPTION_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551228">WDF_CHILD_LIST_CONFIG_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545615">WdfChildListCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547258">WdfFdoInitSetDefaultChildListConfig</a>
 

 

