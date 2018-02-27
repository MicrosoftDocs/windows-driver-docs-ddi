---
UID: NC:wdfchildlist.EVT_WDF_CHILD_LIST_DEVICE_REENUMERATED
title: EVT_WDF_CHILD_LIST_DEVICE_REENUMERATED
author: windows-driver-content
description: A driver's EvtChildListDeviceReenumerated event callback function enables the driver to approve or cancel a reenumeration of a specified device.
old-location: wdf\evtchildlistdevicereenumerated.htm
old-project: wdf
ms.assetid: 404436c3-6ddb-4212-ad51-23a956d7df52
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFDeviceObjectChildListRef_70b8a1c2-d157-4d57-85d3-09566977b649.xml, EVT_WDF_CHILD_LIST_DEVICE_REENUMERATED, EvtChildListDeviceReenumerated, EvtChildListDeviceReenumerated callback function, kmdf.evtchildlistdevicereenumerated, wdf.evtchildlistdevicereenumerated, wdfchildlist/EvtChildListDeviceReenumerated
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	WdfChildlist.h
api_name:
-	EvtChildListDeviceReenumerated
product: Windows
targetos: Windows
req.typenames: WDBGEXTS_THREAD_OS_INFO, *PWDBGEXTS_THREAD_OS_INFO
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
</ol>
The <i>EvtChildListDeviceReenumerated</i> callback function receives pointers to two address descriptions. One points to the address description that is associated with the old device object. The other points to an address description that the callback function must fill in with information that describes the device's current location.

For more information about dynamic enumeration, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/enumerating-the-devices-on-a-bus">Enumerating the Devices on a Bus</a>.


#### Examples

To define an <i>EvtChildListDeviceReenumerated</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtChildListDeviceReenumerated</i> callback function that is named <i>MyChildListDeviceReenumerated</i>, use the <b>EVT_WDF_CHILD_LIST_DEVICE_REENUMERATED</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_CHILD_LIST_DEVICE_REENUMERATED  MyChildListDeviceReenumerated;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
BOOLEAN
 MyChildListDeviceReenumerated (
 WDFCHILDLIST  ChildList,
 WDFDEVICE  OldDevice,
    PWDF_CHILD_ADDRESS_DESCRIPTION_HEADER  OldAddressDescription,
    PWDF_CHILD_ADDRESS_DESCRIPTION_HEADER  NewAddressDescription
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_CHILD_LIST_DEVICE_REENUMERATED</b> function type is defined in the WdfChildlist.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_CHILD_LIST_DEVICE_REENUMERATED</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.




## -see-also

<a href="..\wdfchildlist\ns-wdfchildlist-_wdf_child_address_description_header.md">WDF_CHILD_ADDRESS_DESCRIPTION_HEADER</a>



<a href="..\wdffdo\nf-wdffdo-wdffdoinitsetdefaultchildlistconfig.md">WdfFdoInitSetDefaultChildListConfig</a>



<a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>



<a href="..\wdfchildlist\nc-wdfchildlist-evt_wdf_child_list_create_device.md">EvtChildListCreateDevice</a>



<a href="..\wdfchildlist\nf-wdfchildlist-wdfchildlistcreate.md">WdfChildListCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_CHILD_LIST_DEVICE_REENUMERATED callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

