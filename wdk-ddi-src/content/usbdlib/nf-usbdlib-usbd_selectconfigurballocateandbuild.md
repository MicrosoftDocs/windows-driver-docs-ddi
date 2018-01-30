---
UID: NF:usbdlib.USBD_SelectConfigUrbAllocateAndBuild
title: USBD_SelectConfigUrbAllocateAndBuild function
author: windows-driver-content
description: The USBD_SelectConfigUrbAllocateAndBuild routine allocates and formats a URB structure that is required to select a configuration for a USB device.
old-location: buses\usbd_selectconfigurballocateandbuild.htm
old-project: usbref
ms.assetid: 2B2F721C-9201-472B-8629-352CB212235C
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: usbdlib/USBD_SelectConfigUrbAllocateAndBuild, buses.usbd_selectconfigurballocateandbuild, USBD_SelectConfigUrbAllocateAndBuild, USBD_SelectConfigUrbAllocateAndBuild routine [Buses]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: usbdlib.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Requires WDK for Windows 8. Targets Windows Vista and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Usbdex.lib
req.dll: 
req.irql: DISPATCH_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Usbdex.lib
-	Usbdex.dll
apiname:
-	USBD_SelectConfigUrbAllocateAndBuild
product: Windows
targetos: Windows
req.typenames: "*PUSBCAMD_DEVICE_DATA2, USBCAMD_DEVICE_DATA2"
req.product: Windows 10 or later.
---

# USBD_SelectConfigUrbAllocateAndBuild function


## -description


The <b>USBD_SelectConfigUrbAllocateAndBuild</b> routine allocates and formats a <a href="..\usb\ns-usb-_urb.md">URB</a> structure that is required to select a configuration for a USB device.

<div class="alert"><b>Note</b>  In Windows 8, <b>USBD_SelectConfigUrbAllocateAndBuild</b> replaces <a href="..\usbdlib\nf-usbdlib-usbd_createconfigurationrequestex.md">USBD_CreateConfigurationRequestEx</a> and <a href="..\usbdlib\nf-usbdlib-usbd_createconfigurationrequest.md">USBD_CreateConfigurationRequest</a>.</div>
<div> </div>



## -syntax


````
NTSTATUS USBD_SelectConfigUrbAllocateAndBuild(
  _In_  USBD_HANDLE                   USBDHandle,
  _In_  PUSB_CONFIGURATION_DESCRIPTOR ConfigurationDescriptor,
  _In_  PUSBD_INTERFACE_LIST_ENTRY    InterfaceList,
  _Out_ PURB                          *Urb
);
````


## -parameters




### -param USBDHandle [in]

USBD handle that is retrieved by the client driver in a previous call to  the <a href="..\usbdlib\nf-usbdlib-usbd_createhandle.md">USBD_CreateHandle</a> routine.


### -param ConfigurationDescriptor [in]

Pointer to a caller-allocated <a href="..\usbspec\ns-usbspec-_usb_configuration_descriptor.md">USB_CONFIGURATION_DESCRIPTOR</a> structure that contains the configuration descriptor for the configuration to be selected. Typically, the client driver submits an URB  of the type  URB_FUNCTION_GET_DESCRIPTOR_FROM_DEVICE (see <a href="..\usb\ns-usb-_urb_control_descriptor_request.md">_URB_CONTROL_DESCRIPTOR_REQUEST</a>)     to retrieve information about configurations, interfaces, endpoints, the vendor, and class-specific descriptors from a USB device. When the client driver specifies USB_CONFIGURATION_DESCRIPTOR_TYPE as the descriptor type, the request retrieves all device information in a <b>USB_CONFIGURATION_DESCRIPTOR</b> structure. The driver then passes the received pointer to    the <b>USB_CONFIGURATION_DESCRIPTOR</b> structure in the <i>ConfigurationDescriptor</i> parameter.


### -param InterfaceList [in]

Pointer to the first element of a caller-allocated array of <a href="..\usbdlib\ns-usbdlib-_usbd_interface_list_entry.md">USBD_INTERFACE_LIST_ENTRY</a>    structures. The length of the array depends on the number of interfaces in the configuration descriptor. For more information, see Remarks.


### -param Urb [out]

Pointer to a <a href="..\usb\ns-usb-_urb.md">URB</a> structure that receives the URB allocated by <b>USBD_SelectConfigUrbAllocateAndBuild</b>. The client driver must free the URB when the driver has finished using it by calling <a href="..\usbdlib\nf-usbdlib-usbd_urbfree.md">USBD_UrbFree</a>.


## -returns


The <b>USBD_SelectConfigUrbAllocateAndBuild</b> routine returns an NT status code. 


Possible values include, but are not limited to, the status codes listed in the following table.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The request was successful.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The caller passed an invalid parameter value. <i>USBDHandle</i> or  <i>Urb</i> is NULL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Insufficient memory available to complete the request.

</td>
</tr>
</table> 



## -remarks


Before calling <b>USBD_SelectConfigUrbAllocateAndBuild</b>, the client driver must perform the following tasks: 
<ol>
<li>Get the number of interfaces in the configuration. This information is contained in the <b>bNumInterfaces</b> member of the <a href="..\usbspec\ns-usbspec-_usb_configuration_descriptor.md">USB_CONFIGURATION_DESCRIPTOR</a> structure pointed to by <i>ConfigurationDescriptor</i>.</li>
<li>Create an array of  <a href="..\usbdlib\ns-usbdlib-_usbd_interface_list_entry.md">USBD_INTERFACE_LIST_ENTRY</a> structures. The number  of elements in the array  must be one more than the number of interfaces. Initialize the array by calling <a href="..\wdm\nf-wdm-rtlzeromemory.md">RtlZeroMemory</a>. </li>
<li>Obtain an interface descriptor  for each interface (or its alternate setting)   in the configuration. You can obtain those interface descriptors by calling <a href="..\usbdlib\nf-usbdlib-usbd_parseconfigurationdescriptorex.md">USBD_ParseConfigurationDescriptorEx</a>. </li>
<li>For each element (except  the last element) in the array,  set the <b>InterfaceDescriptor</b> member to the address of an  interface descriptor. For the first element in the array, set the <b>InterfaceDescriptor</b> member to the address of the  interface descriptor that represents the first interface in the configuration. Similarly for the <i>n</i>th element in the array, set the <b>InterfaceDescriptor</b> member to the address of the  interface descriptor that represents the <i>n</i>th interface in the configuration. </li>
<li>The <b>InterfaceDescriptor</b> member of the last element must be set to NULL. </li>
</ol><b>USBD_SelectConfigUrbAllocateAndBuild</b> performs the following tasks: 
<ul>
<li>Creates an URB and fills it with information about the specified configuration, its interfaces and endpoints, and sets the request type to URB_FUNCTION_SELECT_CONFIGURATION.</li>
<li>Fills a <a href="..\usb\ns-usb-_usbd_interface_information.md">USBD_INTERFACE_INFORMATION</a> structure in the URB for each interface.</li>
<li>Sets  the <b>Interface</b> member of the <i>n</i>th element of the caller-provided <a href="..\usbdlib\ns-usbdlib-_usbd_interface_list_entry.md">USBD_INTERFACE_LIST_ENTRY</a>  array to the address of the corresponding <a href="..\usb\ns-usb-_usbd_interface_information.md">USBD_INTERFACE_INFORMATION</a> structure in the URB.</li>
</ul>You can use the received pointer to the <a href="..\usb\ns-usb-_urb.md">URB</a> structure to submit a select-configuration request to the USB driver stack to set the specified configuration. In addition, you can use the <b>Interface</b> member of each <a href="..\usb\ns-usb-_usbd_interface_information.md">USBD_INTERFACE_INFORMATION</a> structure in the array to get information about the interface. Within each <b>USBD_INTERFACE_INFORMATION</b> structure, the  <b>Pipes</b> member is an array of <a href="..\usb\ns-usb-_usbd_pipe_information.md">USBD_PIPE_INFORMATION</a> structures. Each <b>USBD_PIPE_INFORMATION</b> structure contains information about the pipes opened (by the USB driver stack) for the endpoints in that interface. You can  obtain pipe handles from the array and store them for future I/O requests to the device.



## -see-also

<a href="..\usbdlib\nf-usbdlib-usbd_createhandle.md">USBD_CreateHandle</a>

<a href="..\usbdlib\nf-usbdlib-usbd_createconfigurationrequestex.md">USBD_CreateConfigurationRequestEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBD_SelectConfigUrbAllocateAndBuild routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

