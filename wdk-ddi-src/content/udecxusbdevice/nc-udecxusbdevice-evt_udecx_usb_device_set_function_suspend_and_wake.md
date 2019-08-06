---
UID: NC:udecxusbdevice.EVT_UDECX_USB_DEVICE_SET_FUNCTION_SUSPEND_AND_WAKE
title: EVT_UDECX_USB_DEVICE_SET_FUNCTION_SUSPEND_AND_WAKE (udecxusbdevice.h)
description: The USB device emulation class extension (UdeCx) invokes this callback function when it gets a request to change the function state of the specified interface of the virtual USB 3.0 device.
old-location: buses\evt_udecx_usb_device_set_function_suspend_and_wake.htm
tech.root: usbref
ms.assetid: 54484E17-AA96-4152-B672-94C29E53F352
ms.date: 05/07/2018
ms.keywords: EVT_UDECX_USB_DEVICE_SET_FUNCTION_SUSPEND_AND_WAKE, EVT_UDECX_USB_DEVICE_SET_FUNCTION_SUSPEND_AND_WAKE callback, EvtUsbDeviceSetFunctionSuspendAndWake, EvtUsbDeviceSetFunctionSuspendAndWake callback function [Buses], buses.evt_udecx_usb_device_set_function_suspend_and_wake, udecxusbdevice/EvtUsbDeviceSetFunctionSuspendAndWake
ms.topic: callback
f1_keywords:
 - "udecxusbdevice/EvtUsbDeviceSetFunctionSuspendAndWake"
req.header: udecxusbdevice.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
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
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- udecxusbdevice.h
api_name:
- EvtUsbDeviceSetFunctionSuspendAndWake
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UDECX_USB_DEVICE_SET_FUNCTION_SUSPEND_AND_WAKE callback function


## -description


The USB device emulation class extension (UdeCx) invokes this callback function when it gets a request to change the function state of  the specified interface of the virtual USB 3.0 device.


## -parameters




### -param UdecxWdfDevice [in]

A handle to a framework device object that represents the controller to which the USB device is attached. The client driver initialized this object in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/udecxwdfdevice/nf-udecxwdfdevice-udecxwdfdeviceaddusbdeviceemulation">UdecxWdfDeviceAddUsbDeviceEmulation</a>.


### -param UdecxUsbDevice [in]

A handle to UDE device object. The client driver created this object in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/udecxusbdevice/nf-udecxusbdevice-udecxusbdevicecreate">UdecxUsbDeviceCreate</a>.


### -param Interface [in]

This value is the <b>bInterfaceNumber</b> of the interface that is waking up. 


### -param FunctionPower [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/udecxusbdevice/ne-udecxusbdevice-_udecx_usb_device_function_power">UDECX_USB_DEVICE_FUNCTION_POWER</a>-type value that indicates whether the interface can suspend and send wake signal to the host controller.


## -returns



If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE.




## -remarks



The client driver registered the function in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/udecxusbdevice/nf-udecxusbdevice-udecxusbdeviceinitsetstatechangecallbacks">UdecxUsbDeviceInitSetStateChangeCallbacks</a> by supplying a function pointer to its implementation.

In the callback implementation, the client driver for the USB device is expected to perform steps to enter working state. 

This event callback function applies to USB 3.0+ devices. UdeCx invokes this function to notify the client driver of a request to change the power state of a particular function. It also informs the driver whether or not the  function can wake from the new state.

The power request may be completed asynchronously by returning STATUS_PENDING, and then later completing it by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/udecxusbdevice/nf-udecxusbdevice-udecxusbdevicesetfunctionsuspendandwakecomplete">UdecxUsbDeviceSetFunctionSuspendAndWakeComplete</a> with the actual completion code.





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>
 

 

