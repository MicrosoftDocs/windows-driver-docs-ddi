---
UID: NE:wdfchildlist._WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS
title: "_WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS"
author: windows-driver-content
description: The WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS enumeration defines device status values that the framework stores in a driver's WDF_CHILD_RETRIEVE_INFO structure.
old-location: wdf\wdf_child_list_retrieve_device_status.htm
old-project: wdf
ms.assetid: 103f0c51-a7c9-4308-8ae2-d878daf0ff1c
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: WdfChildListRetrieveDeviceSuccess, PWDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS enumeration pointer, PWDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS, WdfChildListRetrieveDeviceNoSuchDevice, kmdf.wdf_child_list_retrieve_device_status, *PWDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS, wdfchildlist/PWDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS, WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS enumeration, wdfchildlist/WdfChildListRetrieveDeviceSuccess, WdfChildListRetrieveDeviceUndefined, WdfChildListRetrieveDeviceNotYetCreated, wdfchildlist/WdfChildListRetrieveDeviceNoSuchDevice, wdfchildlist/WdfChildListRetrieveDeviceNotYetCreated, DFDeviceObjectChildListRef_e8569400-bcce-4c6a-9fe6-23244b35d361.xml, wdfchildlist/WdfChildListRetrieveDeviceUndefined, _WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS, wdfchildlist/WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS, WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS, wdf.wdf_child_list_retrieve_device_status
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: PASSIVE_LEVEL (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfchildlist.h
apiname:
-	WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS
product: Windows
targetos: Windows
req.typenames: WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS, *PWDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS
req.product: Windows 10 or later.
---

# _WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS enumeration


## -description


<p class="CCE_Message">[Applies to KMDF only]

The <b>WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS</b> enumeration defines device status values that the framework stores in a driver's <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_retrieve_info.md">WDF_CHILD_RETRIEVE_INFO</a> structure.


## -syntax


````
typedef enum _WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS { 
  WdfChildListRetrieveDeviceUndefined      = 0,
  WdfChildListRetrieveDeviceSuccess        = 1,
  WdfChildListRetrieveDeviceNotYetCreated  = 2,
  WdfChildListRetrieveDeviceNoSuchDevice   = 3
} WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS, *PWDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS;
````


## -enum-fields




### -field WdfChildListRetrieveDeviceUndefined


### -field WdfChildListRetrieveDeviceSuccess

The <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievenextdevice.md">WdfChildListRetrieveNextDevice</a> or <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievepdo.md">WdfChildListRetrievePdo</a> method successfully retrieved a child device, and a framework device object exists for the device. 


### -field WdfChildListRetrieveDeviceNotYetCreated


<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievenextdevice.md">WdfChildListRetrieveNextDevice</a> or <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievepdo.md">WdfChildListRetrievePdo</a> successfully retrieved a child device, but a framework device object has not been created for the device (because the framework has not called the driver's <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_create_device.md">EvtChildListCreateDevice</a> callback function).


### -field WdfChildListRetrieveDeviceNoSuchDevice


<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievenextdevice.md">WdfChildListRetrieveNextDevice</a> or <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievepdo.md">WdfChildListRetrievePdo</a> was not able to retrieve a child device that matched the search criteria.


## -remarks



The <b>WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS</b> enumeration is used to specify the <b>Status</b> member of a <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_retrieve_info.md">WDF_CHILD_RETRIEVE_INFO</a> structure.




## -see-also

<a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_create_device.md">EvtChildListCreateDevice</a>



<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievenextdevice.md">WdfChildListRetrieveNextDevice</a>



<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievepdo.md">WdfChildListRetrievePdo</a>



<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistretrievepdo.md">WdfChildListRetrievePdo</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_CHILD_LIST_RETRIEVE_DEVICE_STATUS enumeration%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

