---
UID: NF:usbdlib.USBD_SelectConfigUrbAllocateAndBuild
title: USBD_SelectConfigUrbAllocateAndBuild function
author: windows-driver-content
description: The USBD_SelectConfigUrbAllocateAndBuild routine allocates and formats a URB structure that is required to select a configuration for a USB device.
old-location: buses\usbd_selectconfigurballocateandbuild.htm
old-project: usbref
ms.assetid: 2B2F721C-9201-472B-8629-352CB212235C
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: USBD_SelectConfigUrbAllocateAndBuild, USBD_SelectConfigUrbAllocateAndBuild routine [Buses], buses.usbd_selectconfigurballocateandbuild, usbdlib/USBD_SelectConfigUrbAllocateAndBuild
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Usbdex.lib
-	Usbdex.dll
api_name:
-	USBD_SelectConfigUrbAllocateAndBuild
product:
- Windows
targetos: Windows
req.typenames: 
---

# USBD_SelectConfigUrbAllocateAndBuild function


## -description


The <b>USBD_SelectConfigUrbAllocateAndBuild</b> routine allocates and formats a <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a> structure that is required to select a configuration for a USB device.

<div class="alert"><b>Note</b>  In Windows 8, <b>USBD_SelectConfigUrbAllocateAndBuild</b> replaces <a href="https://msdn.microsoft.com/library/windows/hardware/ff539029">USBD_CreateConfigurationRequestEx</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff539025">USBD_CreateConfigurationRequest</a>.</div>
<div> </div>



## -parameters




### -param USBDHandle [in]

USBD handle that is retrieved by the client driver in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406241">USBD_CreateHandle</a> routine.


### -param ConfigurationDescriptor [in]

Pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff539241">USB_CONFIGURATION_DESCRIPTOR</a> structure that contains the configuration descriptor for the configuration to be selected. Typically, the client driver submits an URB  of the type  URB_FUNCTION_GET_DESCRIPTOR_FROM_DEVICE (see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540357">_URB_CONTROL_DESCRIPTOR_REQUEST</a>)     to retrieve information about configurations, interfaces, endpoints, the vendor, and class-specific descriptors from a USB device. When the client driver specifies USB_CONFIGURATION_DESCRIPTOR_TYPE as the descriptor type, the request retrieves all device information in a <b>USB_CONFIGURATION_DESCRIPTOR</b> structure. The driver then passes the received pointer to    the <b>USB_CONFIGURATION_DESCRIPTOR</b> structure in the <i>ConfigurationDescriptor</i> parameter.


### -param InterfaceList [in]

Pointer to the first element of a caller-allocated array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff539076">USBD_INTERFACE_LIST_ENTRY</a>    structures. The length of the array depends on the number of interfaces in the configuration descriptor. For more information, see Remarks.


### -param Urb [out]

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a> structure that receives the URB allocated by <b>USBD_SelectConfigUrbAllocateAndBuild</b>. The client driver must free the URB when the driver has finished using it by calling <a href="https://msdn.microsoft.com/library/windows/hardware/hh406252">USBD_UrbFree</a>.


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
<li>Get the number of interfaces in the configuration. This information is contained in the <b>bNumInterfaces</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539241">USB_CONFIGURATION_DESCRIPTOR</a> structure pointed to by <i>ConfigurationDescriptor</i>.</li>
<li>Create an array of  <a href="https://msdn.microsoft.com/library/windows/hardware/ff539076">USBD_INTERFACE_LIST_ENTRY</a> structures. The number  of elements in the array  must be one more than the number of interfaces. Initialize the array by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff563610">RtlZeroMemory</a>. </li>
<li>Obtain an interface descriptor  for each interface (or its alternate setting)   in the configuration. You can obtain those interface descriptors by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff539102">USBD_ParseConfigurationDescriptorEx</a>. </li>
<li>For each element (except  the last element) in the array,  set the <b>InterfaceDescriptor</b> member to the address of an  interface descriptor. For the first element in the array, set the <b>InterfaceDescriptor</b> member to the address of the  interface descriptor that represents the first interface in the configuration. Similarly for the <i>n</i>th element in the array, set the <b>InterfaceDescriptor</b> member to the address of the  interface descriptor that represents the <i>n</i>th interface in the configuration. </li>
<li>The <b>InterfaceDescriptor</b> member of the last element must be set to NULL. </li>
</ol>
<b>USBD_SelectConfigUrbAllocateAndBuild</b> performs the following tasks: 

<ul>
<li>Creates an URB and fills it with information about the specified configuration, its interfaces and endpoints, and sets the request type to URB_FUNCTION_SELECT_CONFIGURATION.</li>
<li>Fills a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539068">USBD_INTERFACE_INFORMATION</a> structure in the URB for each interface.</li>
<li>Sets  the <b>Interface</b> member of the <i>n</i>th element of the caller-provided <a href="https://msdn.microsoft.com/library/windows/hardware/ff539076">USBD_INTERFACE_LIST_ENTRY</a>  array to the address of the corresponding <a href="https://msdn.microsoft.com/library/windows/hardware/ff539068">USBD_INTERFACE_INFORMATION</a> structure in the URB.</li>
</ul>
You can use the received pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff538923">URB</a> structure to submit a select-configuration request to the USB driver stack to set the specified configuration. In addition, you can use the <b>Interface</b> member of each <a href="https://msdn.microsoft.com/library/windows/hardware/ff539068">USBD_INTERFACE_INFORMATION</a> structure in the array to get information about the interface. Within each <b>USBD_INTERFACE_INFORMATION</b> structure, the  <b>Pipes</b> member is an array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff539114">USBD_PIPE_INFORMATION</a> structures. Each <b>USBD_PIPE_INFORMATION</b> structure contains information about the pipes opened (by the USB driver stack) for the endpoints in that interface. You can  obtain pipe handles from the array and store them for future I/O requests to the device.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539029">USBD_CreateConfigurationRequestEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406241">USBD_CreateHandle</a>
 

 

