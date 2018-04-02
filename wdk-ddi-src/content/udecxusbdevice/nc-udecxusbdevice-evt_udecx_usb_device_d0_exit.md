---
UID: NC:udecxusbdevice.EVT_UDECX_USB_DEVICE_D0_EXIT
title: EVT_UDECX_USB_DEVICE_D0_EXIT
author: windows-driver-content
description: The USB device emulation class extension (UdeCx) invokes this callback function when it gets a request to send the virtual USB device to a low power state.
old-location: buses\evt_udecx_usb_device_d0_exit.htm
old-project: usbref
ms.assetid: CC2878DC-66EC-4493-8188-3B6BAEA928DF
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: EVT_UDECX_USB_DEVICE_D0_EXIT, EvtUsbDeviceLinkPowerExit, EvtUsbDeviceLinkPowerExit callback function [Buses], buses.evt_udecx_usb_device_d0_exit, udecxusbdevice/EvtUsbDeviceLinkPowerExit
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	udecxusbdevice.h
api_name:
-	EvtUsbDeviceLinkPowerExit
product:
- Windows
targetos: Windows
req.typenames: USB_DEVICE_PORT_PATH, *PUSB_DEVICE_PORT_PATH
req.product: Windows 10 or later.
---

# EVT_UDECX_USB_DEVICE_D0_EXIT callback


## -description


The USB device emulation class extension (UdeCx) invokes this callback function when it gets a request to send the virtual USB device to a low power state.


## -parameters




### -param UdecxWdfDevice [in]

A handle to a framework device object that represents the controller to which the USB device is attached. The client driver initialized this object in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt627990">UdecxWdfDeviceAddUsbDeviceEmulation</a>.


### -param UdecxUsbDevice [in]

A handle to UDE device object. The client driver created this object in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt595959">UdecxUsbDeviceCreate</a>.


### -param WakeSetting [in]

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt628004">UDECX_USB_DEVICE_WAKE_SETTING</a>-type value that indicates remote wake capability of the USB device.


## -returns



If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE.




## -remarks



The client driver registered the function in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt627972">UdecxUsbDeviceInitSetStateChangeCallbacks</a> by supplying a function pointer to its implementation.

In the callback implementation, the client driver for the USB device is expected to perform steps to send the device to a low power state. In this function, the driver can initiate its wake-up from a low link power state, function suspend, or both.
To do so, the driver for a USB 2.0 device must call the <a href="https://msdn.microsoft.com/library/windows/hardware/mt627982">UdecxUsbDeviceSignalWake</a> method.  USB 3.0 devices must use <a href="https://msdn.microsoft.com/library/windows/hardware/mt627981">UdecxUsbDeviceSignalFunctionWake</a>.

The power request may be completed asynchronously by returning STATUS_PENDING, and then later calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt627974">UdecxUsbDeviceLinkPowerExitComplete</a> with the actual completion code.





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595910">EVT_UDECX_USB_DEVICE_D0_ENTRY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt627974">UdecxUsbDeviceLinkPowerExitComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt627982">UdecxUsbDeviceSignalWake</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>
 

 

