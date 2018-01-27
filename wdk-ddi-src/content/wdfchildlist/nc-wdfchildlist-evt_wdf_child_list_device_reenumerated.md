---
UID: NC:wdfchildlist.EVT_WDF_CHILD_LIST_DEVICE_REENUMERATED
title: EVT_WDF_CHILD_LIST_DEVICE_REENUMERATED
author: windows-driver-content
description: A driver's EvtChildListDeviceReenumerated event callback function enables the driver to approve or cancel a reenumeration of a specified device.
old-location: wdf\evtchildlistdevicereenumerated.htm
old-project: wdf
ms.assetid: 404436c3-6ddb-4212-ad51-23a956d7df52
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtchildlistdevicereenumerated, EvtChildListDeviceReenumerated callback function, EvtChildListDeviceReenumerated, EVT_WDF_CHILD_LIST_DEVICE_REENUMERATED, EVT_WDF_CHILD_LIST_DEVICE_REENUMERATED, wdfchildlist/EvtChildListDeviceReenumerated, DFDeviceObjectChildListRef_70b8a1c2-d157-4d57-85d3-09566977b649.xml, kmdf.evtchildlistdevicereenumerated
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	WdfChildlist.h
apiname: 
-	EvtChildListDeviceReenumerated
product: Windows
targetos: Windows
req.typenames: *PWDBGEXTS_THREAD_OS_INFO, WDBGEXTS_THREAD_OS_INFO
req.product: Windows 10 or later.
---

# EVT_WDF_CHILD_LIST_DEVICE_REENUMERATED callback


## -description


<p class="CCE_Message">[Applies to KMDF only]

A driver's <i>EvtChildListDeviceReenumerated</i> event callback function enables the driver to approve or cancel a reenumeration of a specified device. 


## -prototype


````
EVT_WDF_CHILD_LIST_DEVICE_REENUMERATED EvtChildListDeviceReenumerated;

BOOLEAN EvtChildListDeviceReenumerated(
  _In_  WDFCHILDLIST                          ChildList,
  _In_  WDFDEVICE                             OldDevice,
  _In_  PWDF_CHILD_ADDRESS_DESCRIPTION_HEADER OldAddressDescription,
  _Out_ PWDF_CHILD_ADDRESS_DESCRIPTION_HEADER NewAddressDescription
)
{ ... }
````


## -parameters




### -param ChildList [in]

A handle to a framework child list object.


### -param OldDevice [in]

A handle to a framework device object.


### -param OldAddressDescription [in]

A pointer to a <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_address_description_header.md">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a> structure that identifies a child address description. This structure contains address information that was relevant before the device was reenumerated.


### -param NewAddressDescription [out]

A pointer to a <a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_address_description_header.md">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a> structure that identifies a child address description. The callback function fills in this structure with new address information about the device.


## -returns


The <i>EvtChildListDeviceReenumerated</i> callback function returns <b>TRUE</b> to approve the reenumeration or <b>FALSE</b> to cancel it. 



## -remarks


If a bus driver is using <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dynamic-enumeration">dynamic enumeration</a>, it can register an <i>EvtChildListDeviceReenumerated</i> callback function by calling <a href="..\wdffdo\nf-wdffdo-wdffdoinitsetdefaultchildlistconfig.md">WdfFdoInitSetDefaultChildListConfig</a> or <a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistcreate.md">WdfChildListCreate</a>.

Framework-based bus drivers can receive a request from a function driver to reenumerate a particular child device. For more information about these requests, see <a href="https://msdn.microsoft.com/3719ffa7-2daf-4716-a183-531837be99aa">Handling Enumeration Requests</a>. 

The bus driver's <i>EvtChildListDeviceReenumerated</i> callback function enables the driver to approve or cancel the reenumeration. The <i>OldDevice</i> parameter identifies the device, and the <i>ChildList</i> parameter identifies the child list that the device is a member of. If the callback function returns <b>TRUE</b> to approve the reenumeration, or if the callback function does not exist, the framework does the following:
<ol>
<li>
Removes the device's framework device object (which is identified by <i>OldDevice</i>) but retains the device's identification description.

</li>
<li>
Calls the driver's <a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_create_device.md">EvtChildListCreateDevice</a> callback function, passing the saved identification description, so that the callback function can call <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a> to create a new framework device object.

</li>
</ol>The <i>EvtChildListDeviceReenumerated</i> callback function receives pointers to two address descriptions. One points to the address description that is associated with the old device object. The other points to an address description that the callback function must fill in with information that describes the device's current location.

For more information about dynamic enumeration, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/enumerating-the-devices-on-a-bus">Enumerating the Devices on a Bus</a>.



## -see-also

<a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>

<a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_create_device.md">EvtChildListCreateDevice</a>

<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistcreate.md">WdfChildListCreate</a>

<a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_address_description_header.md">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a>

<a href="..\wdffdo\nf-wdffdo-wdffdoinitsetdefaultchildlistconfig.md">WdfFdoInitSetDefaultChildListConfig</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_CHILD_LIST_DEVICE_REENUMERATED callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

