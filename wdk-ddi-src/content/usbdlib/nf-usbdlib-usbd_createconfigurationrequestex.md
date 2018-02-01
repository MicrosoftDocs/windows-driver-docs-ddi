---
UID: NF:usbdlib.USBD_CreateConfigurationRequestEx
title: USBD_CreateConfigurationRequestEx function
author: windows-driver-content
description: The USBD_CreateConfigurationRequestEx routine allocates and formats a URB to select a configuration for a USB device.USBD_CreateConfigurationRequestEx replaces USBD_CreateConfigurationRequest.
old-location: buses\usbd_createconfigurationrequestex.htm
old-project: usbref
ms.assetid: 9683b171-4f2e-4a18-89b7-76d49001be37
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: usbfunc_d0c1e002-ed01-4bd4-98f0-b4b2d6da2ca6.xml, buses.usbd_createconfigurationrequestex, usbdlib/USBD_CreateConfigurationRequestEx, USBD_CreateConfigurationRequestEx routine [Buses], USBD_CreateConfigurationRequestEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: usbdlib.h
req.include-header: Usbdlib.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.lib: Usbd.lib
req.dll: 
req.irql: DISPATCH_LEVEL (See Remarks)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Usbd.lib
-	Usbd.dll
apiname:
-	USBD_CreateConfigurationRequestEx
product: Windows
targetos: Windows
req.typenames: USBCAMD_DEVICE_DATA2, *PUSBCAMD_DEVICE_DATA2
req.product: Windows 10 or later.
---

# USBD_CreateConfigurationRequestEx function


## -description



   The <b>USBD_CreateConfigurationRequestEx</b> routine allocates and formats a <a href="..\usb\ns-usb-_urb.md">URB</a> to select a configuration for a USB device.

<b>USBD_CreateConfigurationRequestEx</b> replaces <a href="..\usbdlib\nf-usbdlib-usbd_createconfigurationrequest.md">USBD_CreateConfigurationRequest</a>.


## -syntax


````
PURB USBD_CreateConfigurationRequestEx(
  _In_ PUSB_CONFIGURATION_DESCRIPTOR ConfigurationDescriptor,
  _In_ PUSBD_INTERFACE_LIST_ENTRY    InterfaceList
);
````


## -parameters




### -param ConfigurationDescriptor [in]

Pointer to a caller-allocated <a href="..\usbspec\ns-usbspec-_usb_configuration_descriptor.md">USB_CONFIGURATION_DESCRIPTOR</a> structure that contains the configuration descriptor for the configuration to be selected. Typically, the client driver submits a URB  of the type  URB_FUNCTION_GET_DESCRIPTOR_FROM_DEVICE (see <a href="..\usb\ns-usb-_urb_control_descriptor_request.md">_URB_CONTROL_DESCRIPTOR_REQUEST</a>)     to retrieve information about configurations, interfaces, endpoints, the vendor, and class-specific descriptors from a USB device. When the client driver specifies USB_CONFIGURATION_DESCRIPTOR_TYPE as the descriptor type, the request retrieves all device information in a <b>USB_CONFIGURATION_DESCRIPTOR</b> structure. The driver then passes the received pointer to    the <b>USB_CONFIGURATION_DESCRIPTOR</b> structure in the <i>ConfigurationDescriptor</i> parameter.


### -param InterfaceList [in]

Pointer to the first element of a caller-allocated array of <a href="..\usbdlib\ns-usbdlib-_usbd_interface_list_entry.md">USBD_INTERFACE_LIST_ENTRY</a>    structures. The length of the array depends on the number of interfaces in the configuration descriptor. The number  of elements in the array  must be one more than the number of interfaces in the configuration. Initialize the array by calling <a href="..\wdm\nf-wdm-rtlzeromemory.md">RtlZeroMemory</a>. The <b>InterfaceDescriptor</b> member of the last element in the array must be set to <b>NULL</b>. 


## -returns


<b>USBD_CreateConfigurationRequestEx</b> allocates a <a href="..\usb\ns-usb-_urb.md">URB</a> structure, formats it for the URB_FUNCTION_SELECT_CONFIGURATION request (select-configuration request), and returns a pointer to the <b>URB</b>. The client driver can then use the returned <b>URB</b> to send the select-configuration request  to the host controller driver to set the configuration. You must free the <b>URB</b> when you have finished using it.



## -remarks


For information about how to build a select-configuration reqeuest and code example, see <a href="https://msdn.microsoft.com/library/windows/hardware/gg615081">How to Select a Configuration for a USB Device</a>.

The returned value is a pointer to the <a href="..\usb\ns-usb-_urb.md">URB</a> structure that you can use to submit a select-configuration request to the host controller driver to set the specified configuration.

After the USB driver stack completes the select-configuration request, you can inspect the  <a href="..\usb\ns-usb-_usbd_interface_information.md">USBD_INTERFACE_INFORMATION</a> structures.  The <b>Pipes</b> member of <b>USBD_INTERFACE_INFORMATION</b> points to an array of <a href="..\usb\ns-usb-_usbd_pipe_information.md">USBD_PIPE_INFORMATION</a> structures. The USB bus driver fills the array of <b>USBD_PIPE_INFORMATION</b> structures with information about the  pipes associated with the endpoints of the interface. The client driver can obtain pipe handles from the <code>Pipes[i].PipeHandle</code> and use them to send I/O requests to specific pipes. 

After you have completed all operations with the returned <a href="..\usb\ns-usb-_urb.md">URB</a>, you must free the <b>URB</b> by calling <a href="..\wdm\nf-wdm-exfreepool.md">ExFreePool</a>. 

You can  allocate the configuration descriptor and the array from nonpaged or paged pool. Callers of this routine can run at IRQL &lt;= DISPATCH_LEVEL if the memory pointed to by <i>ConfigurationDescriptor</i> and <i>InterfaceList</i> is allocated from nonpaged pool. Otherwise, callers must run at IRQL &lt; DISPATCH_LEVEL.



## -see-also

<a href="..\usb\ns-usb-_usbd_interface_information.md">USBD_INTERFACE_INFORMATION</a>

<a href="..\usb\ns-usb-_urb_select_configuration.md">_URB_SELECT_CONFIGURATION</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540134">USB device driver programming reference</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/gg615081">How to Select a Configuration for a USB Device</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBD_CreateConfigurationRequestEx routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

