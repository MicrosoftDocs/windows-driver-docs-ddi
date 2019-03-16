---
UID: NE:wdfchildlist._WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS
title: _WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS (wdfchildlist.h)
description: The WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS enumeration defines device status values that the framework stores in a driver's WDF_CHILD_RETRIEVE_INFO structure.
old-location: wdf\wdf_child_list_retrieve_device_status.htm
tech.root: wdf
ms.assetid: 103f0c51-a7c9-4308-8ae2-d878daf0ff1c
ms.date: 02/26/2018
ms.keywords: "*PWDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS, DFDeviceObjectChildListRef_e8569400-bcce-4c6a-9fe6-23244b35d361.xml, PWDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS, PWDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS enumeration pointer, WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS, WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS enumeration, WdfChildListRetrieveDeviceNoSuchDevice, WdfChildListRetrieveDeviceNotYetCreated, WdfChildListRetrieveDeviceSuccess, WdfChildListRetrieveDeviceUndefined, _WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS, kmdf.wdf_child_list_retrieve_device_status, wdf.wdf_child_list_retrieve_device_status, wdfchildlist/PWDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS, wdfchildlist/WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS, wdfchildlist/WdfChildListRetrieveDeviceNoSuchDevice, wdfchildlist/WdfChildListRetrieveDeviceNotYetCreated, wdfchildlist/WdfChildListRetrieveDeviceSuccess, wdfchildlist/WdfChildListRetrieveDeviceUndefined"
ms.topic: enum
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
- WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS
product:
- Windows
targetos: Windows
req.typenames: WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS, *PWDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS
---

# _WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS enumeration


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS</b> enumeration defines device status values that the framework stores in a driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff551234">WDF_CHILD_RETRIEVE_INFO</a> structure.


## -enum-fields




### -field WdfChildListRetrieveDeviceUndefined


### -field WdfChildListRetrieveDeviceSuccess

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff545655">WdfChildListRetrieveNextDevice</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff545663">WdfChildListRetrievePdo</a> method successfully retrieved a child device, and a framework device object exists for the device. 


### -field WdfChildListRetrieveDeviceNotYetCreated


<a href="https://msdn.microsoft.com/library/windows/hardware/ff545655">WdfChildListRetrieveNextDevice</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff545663">WdfChildListRetrievePdo</a> successfully retrieved a child device, but a framework device object has not been created for the device (because the framework has not called the driver's <a href="https://msdn.microsoft.com/296fbe06-1680-43a8-b5c3-1a1faa19c6c3">EvtChildListCreateDevice</a> callback function).


### -field WdfChildListRetrieveDeviceNoSuchDevice


<a href="https://msdn.microsoft.com/library/windows/hardware/ff545655">WdfChildListRetrieveNextDevice</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff545663">WdfChildListRetrievePdo</a> was not able to retrieve a child device that matched the search criteria.


## -remarks



The <b>WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS</b> enumeration is used to specify the <b>Status</b> member of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551234">WDF_CHILD_RETRIEVE_INFO</a> structure.




## -see-also




<a href="https://msdn.microsoft.com/296fbe06-1680-43a8-b5c3-1a1faa19c6c3">EvtChildListCreateDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551234">WDF_CHILD_RETRIEVE_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545655">WdfChildListRetrieveNextDevice</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545663">WdfChildListRetrievePdo</a>
 

 

