---
UID: NC:wdfchildlist.EVT_WDF_CHILD_LIST_DEVICE_REENUMERATED
title: EVT_WDF_CHILD_LIST_DEVICE_REENUMERATED (wdfchildlist.h)
description: A driver's EvtChildListDeviceReenumerated event callback function enables the driver to approve or cancel a reenumeration of a specified device.
old-location: wdf\evtchildlistdevicereenumerated.htm
tech.root: wdf
ms.assetid: 404436c3-6ddb-4212-ad51-23a956d7df52
ms.date: 02/26/2018
keywords: ["EVT_WDF_CHILD_LIST_DEVICE_REENUMERATED callback function"]
ms.keywords: DFDeviceObjectChildListRef_70b8a1c2-d157-4d57-85d3-09566977b649.xml, EVT_WDF_CHILD_LIST_DEVICE_REENUMERATED, EVT_WDF_CHILD_LIST_DEVICE_REENUMERATED callback, EvtChildListDeviceReenumerated, EvtChildListDeviceReenumerated callback function, kmdf.evtchildlistdevicereenumerated, wdf.evtchildlistdevicereenumerated, wdfchildlist/EvtChildListDeviceReenumerated
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
 - EVT_WDF_CHILD_LIST_DEVICE_REENUMERATED
 - wdfchildlist/EVT_WDF_CHILD_LIST_DEVICE_REENUMERATED
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - WdfChildlist.h
api_name:
 - EvtChildListDeviceReenumerated
---

# EVT_WDF_CHILD_LIST_DEVICE_REENUMERATED callback function


## -description

<p class="CCE_Message">[Applies to KMDF only]</p>

A driver's <i>EvtChildListDeviceReenumerated</i> event callback function enables the driver to approve or cancel a reenumeration of a specified device.

## -parameters

### -param ChildList 

[in]
A handle to a framework child list object.

### -param OldDevice 

[in]
A handle to a framework device object.

### -param OldAddressDescription 

[in]
Optional pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_address_description_header">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a> structure that identifies a child address description, or NULL. If provided, this structure contains address information that was relevant before the device was reenumerated.

### -param NewAddressDescription 

[out]
Optional pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_address_description_header">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a> structure that identifies a child address description, or NULL. If provided, the callback function fills in this structure with new address information about the device.

## -returns

The <i>EvtChildListDeviceReenumerated</i> callback function returns <b>TRUE</b> to approve the reenumeration or <b>FALSE</b> to cancel it.

## -remarks

If a bus driver is using <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/dynamic-enumeration">dynamic enumeration</a>, it can register an <i>EvtChildListDeviceReenumerated</i> callback function by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitsetdefaultchildlistconfig">WdfFdoInitSetDefaultChildListConfig</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistcreate">WdfChildListCreate</a>.

Framework-based bus drivers can receive a request from a function driver to reenumerate a particular child device. For more information about these requests, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/handling-enumeration-requests">Handling Enumeration Requests</a>. 

The bus driver's <i>EvtChildListDeviceReenumerated</i> callback function enables the driver to approve or cancel the reenumeration. The <i>OldDevice</i> parameter identifies the device, and the <i>ChildList</i> parameter identifies the child list that the device is a member of. If the callback function returns <b>TRUE</b> to approve the reenumeration, or if the callback function does not exist, the framework does the following:

<ol>
<li>
Removes the device's framework device object (which is identified by <i>OldDevice</i>) but retains the device's identification description.

</li>
<li>
Calls the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_create_device">EvtChildListCreateDevice</a> callback function, passing the saved identification description, so that the callback function can call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a> to create a new framework device object.

</li>
</ol>
If the bus driver uses address descriptions, the <i>EvtChildListDeviceReenumerated</i> callback function receives pointers to two address descriptions. One points to the address description that is associated with the old device object. The other points to an address description that the callback function must fill in with information that describes the device's current location.

For more information about dynamic enumeration, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/enumerating-the-devices-on-a-bus">Enumerating the Devices on a Bus</a>.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nc-wdfchildlist-evt_wdf_child_list_create_device">EvtChildListCreateDevice</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/ns-wdfchildlist-_wdf_child_address_description_header">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfchildlist/nf-wdfchildlist-wdfchildlistcreate">WdfChildListCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdffdo/nf-wdffdo-wdffdoinitsetdefaultchildlistconfig">WdfFdoInitSetDefaultChildListConfig</a>

