---
UID: NC:udecxusbdevice.EVT_UDECX_USB_DEVICE_D0_EXIT
title: EVT_UDECX_USB_DEVICE_D0_EXIT (udecxusbdevice.h)
description: The USB device emulation class extension (UdeCx) invokes this callback function when it gets a request to send the virtual USB device to a low power state.
old-location: buses\evt_udecx_usb_device_d0_exit.htm
tech.root: usbref
ms.assetid: CC2878DC-66EC-4493-8188-3B6BAEA928DF
ms.date: 05/07/2018
ms.keywords: EVT_UDECX_USB_DEVICE_D0_EXIT, EVT_UDECX_USB_DEVICE_D0_EXIT callback, EvtUsbDeviceLinkPowerExit, EvtUsbDeviceLinkPowerExit callback function [Buses], buses.evt_udecx_usb_device_d0_exit, udecxusbdevice/EvtUsbDeviceLinkPowerExit
ms.topic: callback
f1_keywords:
 - "udecxusbdevice/EvtUsbDeviceLinkPowerExit"
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
- EvtUsbDeviceLinkPowerExit
product:
- Windows
targetos: Windows
req.typenames: 
---

# EVT_UDECX_USB_DEVICE_D0_EXIT callback function


## -description


The USB device emulation class extension (UdeCx) invokes this callback function when it gets a request to send the virtual USB device to a low power state.


## -parameters




### -param UdecxWdfDevice [in]

A handle to a framework device object that represents the controller to which the USB device is attached. The client driver initialized this object in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/udecxwdfdevice/nf-udecxwdfdevice-udecxwdfdeviceaddusbdeviceemulation">UdecxWdfDeviceAddUsbDeviceEmulation</a>.


### -param UdecxUsbDevice [in]

A handle to UDE device object. The client driver created this object in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/udecxusbdevice/nf-udecxusbdevice-udecxusbdevicecreate">UdecxUsbDeviceCreate</a>.


### -param WakeSetting [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/udecxusbdevice/ne-udecxusbdevice-_udecx_usb_device_wake_setting">UDECX_USB_DEVICE_WAKE_SETTING</a>-type value that indicates remote wake capability of the USB device.


## -returns



If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE.




## -remarks



The client driver registered the function in a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/udecxusbdevice/nf-udecxusbdevice-udecxusbdeviceinitsetstatechangecallbacks">UdecxUsbDeviceInitSetStateChangeCallbacks</a> by supplying a function pointer to its implementation.

In the callback implementation, the client driver for the USB device is expected to perform steps to send the device to a low power state. In this function, the driver can initiate its wake-up from a low link power state, function suspend, or both.
To do so, the driver for a USB 2.0 device must call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/udecxusbdevice/nf-udecxusbdevice-udecxusbdevicesignalwake">UdecxUsbDeviceSignalWake</a> method.  USB 3.0 devices must use <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/udecxusbdevice/nf-udecxusbdevice-udecxusbdevicesignalfunctionwake">UdecxUsbDeviceSignalFunctionWake</a>.

The power request may be completed asynchronously by returning STATUS_PENDING, and then later calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/udecxusbdevice/nf-udecxusbdevice-udecxusbdevicelinkpowerexitcomplete">UdecxUsbDeviceLinkPowerExitComplete</a> with the actual completion code.





## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/udecxusbdevice/nc-udecxusbdevice-evt_udecx_usb_device_d0_entry">EVT_UDECX_USB_DEVICE_D0_ENTRY</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/udecxusbdevice/nf-udecxusbdevice-udecxusbdevicelinkpowerexitcomplete">UdecxUsbDeviceLinkPowerExitComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/udecxusbdevice/nf-udecxusbdevice-udecxusbdevicesignalwake">UdecxUsbDeviceSignalWake</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>
 

 

