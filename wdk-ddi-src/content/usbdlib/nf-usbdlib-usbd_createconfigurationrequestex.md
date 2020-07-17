---
UID: NF:usbdlib.USBD_CreateConfigurationRequestEx
title: USBD_CreateConfigurationRequestEx function (usbdlib.h)
description: The USBD_CreateConfigurationRequestEx routine allocates and formats a URB to select a configuration for a USB device.USBD_CreateConfigurationRequestEx replaces USBD_CreateConfigurationRequest.
old-location: buses\usbd_createconfigurationrequestex.htm
tech.root: usbref
ms.assetid: 9683b171-4f2e-4a18-89b7-76d49001be37
ms.date: 05/07/2018
keywords: ["USBD_CreateConfigurationRequestEx function"]
ms.keywords: USBD_CreateConfigurationRequestEx, USBD_CreateConfigurationRequestEx routine [Buses], buses.usbd_createconfigurationrequestex, usbdlib/USBD_CreateConfigurationRequestEx, usbfunc_d0c1e002-ed01-4bd4-98f0-b4b2d6da2ca6.xml
f1_keywords:
 - "usbdlib/USBD_CreateConfigurationRequestEx"
 - "USBD_CreateConfigurationRequestEx"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Usbd.lib
- Usbd.dll
api_name:
- USBD_CreateConfigurationRequestEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# USBD_CreateConfigurationRequestEx function


## -description



   The <b>USBD_CreateConfigurationRequestEx</b> routine allocates and formats a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a> to select a configuration for a USB device.

<b>USBD_CreateConfigurationRequestEx</b> replaces <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_createconfigurationrequest">USBD_CreateConfigurationRequest</a>.


## -parameters




### -param ConfigurationDescriptor [in]

Pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_configuration_descriptor">USB_CONFIGURATION_DESCRIPTOR</a> structure that contains the configuration descriptor for the configuration to be selected. Typically, the client driver submits a URB  of the type  URB_FUNCTION_GET_DESCRIPTOR_FROM_DEVICE (see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_control_descriptor_request">_URB_CONTROL_DESCRIPTOR_REQUEST</a>)     to retrieve information about configurations, interfaces, endpoints, the vendor, and class-specific descriptors from a USB device. When the client driver specifies USB_CONFIGURATION_DESCRIPTOR_TYPE as the descriptor type, the request retrieves all device information in a <b>USB_CONFIGURATION_DESCRIPTOR</b> structure. The driver then passes the received pointer to    the <b>USB_CONFIGURATION_DESCRIPTOR</b> structure in the <i>ConfigurationDescriptor</i> parameter.


### -param InterfaceList [in]

Pointer to the first element of a caller-allocated array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/ns-usbdlib-_usbd_interface_list_entry">USBD_INTERFACE_LIST_ENTRY</a>    structures. The length of the array depends on the number of interfaces in the configuration descriptor. The number  of elements in the array  must be one more than the number of interfaces in the configuration. Initialize the array by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-rtlzeromemory">RtlZeroMemory</a>. The <b>InterfaceDescriptor</b> member of the last element in the array must be set to <b>NULL</b>. 


## -returns



<b>USBD_CreateConfigurationRequestEx</b> allocates a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a> structure, formats it for the URB_FUNCTION_SELECT_CONFIGURATION request (select-configuration request), and returns a pointer to the <b>URB</b>. The client driver can then use the returned <b>URB</b> to send the select-configuration request  to the host controller driver to set the configuration. You must free the <b>URB</b> when you have finished using it.




## -remarks



For information about how to build a select-configuration reqeuest and code example, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">How to Select a Configuration for a USB Device</a>.

The returned value is a pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a> structure that you can use to submit a select-configuration request to the host controller driver to set the specified configuration.

After the USB driver stack completes the select-configuration request, you can inspect the  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_usbd_interface_information">USBD_INTERFACE_INFORMATION</a> structures.  The <b>Pipes</b> member of <b>USBD_INTERFACE_INFORMATION</b> points to an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_usbd_pipe_information">USBD_PIPE_INFORMATION</a> structures. The USB bus driver fills the array of <b>USBD_PIPE_INFORMATION</b> structures with information about the  pipes associated with the endpoints of the interface. The client driver can obtain pipe handles from the <code>Pipes[i].PipeHandle</code> and use them to send I/O requests to specific pipes. 

After you have completed all operations with the returned <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a>, you must free the <b>URB</b> by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/nf-ntddk-exfreepool">ExFreePool</a>. 

You can  allocate the configuration descriptor and the array from nonpaged or paged pool. Callers of this routine can run at IRQL <= DISPATCH_LEVEL if the memory pointed to by <i>ConfigurationDescriptor</i> and <i>InterfaceList</i> is allocated from nonpaged pool. Otherwise, callers must run at IRQL < DISPATCH_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">How to Select a Configuration for a USB Device</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_usbref/">USB device driver programming reference</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_usbd_interface_information">USBD_INTERFACE_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_select_configuration">_URB_SELECT_CONFIGURATION</a>
 

 

