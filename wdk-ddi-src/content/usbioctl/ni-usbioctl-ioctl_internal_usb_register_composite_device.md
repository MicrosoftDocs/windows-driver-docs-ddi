---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE
title: IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE
author: windows-driver-content
description: The IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE I/O request registers the driver of a USB multi-function device (composite driver) with the underlying USB driver stack.
old-location: buses\ioctl_internal_usb_register_composite_driver.htm
old-project: usbref
ms.assetid: 5ADCD625-485C-4E18-B022-BA1611F87EA9
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE, IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE control code [Buses], buses.ioctl_internal_usb_register_composite_driver, usbioctl/IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Usbioctl.h
api_name:
-	IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE
product:
- Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE IOCTL


## -description



The <b>IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE</b> 
   I/O request registers the driver of a USB  multi-function device (composite driver) with the underlying USB driver stack.



This request is sent by a driver that replaces the Microsoft-provided composite driver, Usbccgp.sys, and implements the function suspend and remote wake-up feature, per the Universal Serial Bus (USB) 3.0 specification.



<b>IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE</b> is a kernel-mode I/O control request. This request targets the USB hub physical device object (PDO). This request must be sent at an interrupt request level (IRQL) of PASSIVE_LEVEL.


## -ioctlparameters




### -input-buffer

<b>Parameters.Others.Argument1</b> is a pointer to a caller-allocated and initialized <a href="https://msdn.microsoft.com/library/windows/hardware/hh450898">REGISTER_COMPOSITE_DEVICE</a> structure that contains information about the parent driver. To initialize the structure, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406229">USBD_BuildRegisterCompositeDevice</a> routine.


       The <b>AssociatedIrp.SystemBuffer</b> member points to a caller-allocated buffer that is large enough to hold an array of function handles (typed USBD_FUNCTION_HANDLE) for functions in the USB composite device. The number of elements in the array is indicated by the <b>FunctionCount</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/hh450898">REGISTER_COMPOSITE_DEVICE</a>. To obtain the number of functions, inspect the descriptors returned by a get-configuration request.


### -input-buffer-length

The size of a <a href="https://msdn.microsoft.com/library/windows/hardware/hh450898">REGISTER_COMPOSITE_DEVICE</a> structure.


### -output-buffer

On output, the buffer pointed to by <b>AssociatedIrp.SystemBuffer</b> member is filled with function handles for functions in the multi-function device.


### -output-buffer-length

The size of function handles for functions in the device.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The USB driver stack sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS if the request completes successfully. STATUS_SUCCESS indicates that the function handles are valid.

In case of an error,  <b>Irp-&gt;IoStatus.Status</b> contains an appropriate error status. For example, if the composite driver sends the request more than once, the <b>Status</b> is set to STATUS_INVALID_DEVICE_REQUEST.


## -remarks



The purpose of <b>IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE</b> is for the composite driver to send a registration request to the USB driver stack. In the registration request, the composite driver specifies the number of functions supported by the device. Therefore, you must send the <b>IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE</b> request  after determining the number of functions.  Typically, that information is retrieved in the composite driver's start-device routine (<a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a>). Note that number of interfaces in a configuration <i>can</i> indicate the number of functions, but not always. Certain multi-function devices expose multiple interfaces related to one function. To obtain the number of functions, you must inspect various descriptors that are related to a particular configuration. Those descriptors can be obtained through a get-descriptor request. 

In response to the registration request, the USB driver stack provides a list of handles for the functions in the device. For a code example, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh450897">How to Register a Composite Device</a>.

After the composite driver is registered, the driver can configure the remote wake-up feature. By using the function handle, the composite driver can send a request (see <a href="https://msdn.microsoft.com/library/windows/hardware/hh450856">IOCTL_INTERNAL_USB_REQUEST_REMOTE_WAKE_NOTIFICATION</a>)  to get remote wake-up notifications from the USB driver stack, when the associated function sends a resume signal. 

In order to remove the composite driver's association with the USB driver stack and release all resources that are allocated for registration, the driver must send the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450855">IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE</a> request. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450897">How to Register a Composite Device</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450855">IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE</a>
 

 

