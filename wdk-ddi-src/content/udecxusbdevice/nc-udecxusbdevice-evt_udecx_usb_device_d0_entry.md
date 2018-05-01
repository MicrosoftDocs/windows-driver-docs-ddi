---
UID: NC:udecxusbdevice.EVT_UDECX_USB_DEVICE_D0_ENTRY
title: EVT_UDECX_USB_DEVICE_D0_ENTRY
author: windows-driver-content
description: The USB device emulation class extension (UdeCx) invokes this callback function when it gets a request to bring the virtual USB device out of a low power state to working state.
old-location: buses\evt_udecx_usb_device_d0_entry.htm
old-project: usbref
ms.assetid: 92CEEAF3-BD70-4B1C-8385-00720A195E50
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: EVT_UDECX_USB_DEVICE_D0_ENTRY, EVT_UDECX_USB_DEVICE_D0_ENTRY callback, EvtUsbDeviceLinkPowerEntry, EvtUsbDeviceLinkPowerEntry callback function [Buses], buses.evt_udecx_usb_device_d0_entry, udecxusbdevice/EvtUsbDeviceLinkPowerEntry
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
-	EvtUsbDeviceLinkPowerEntry
product: Windows
targetos: Windows
req.typenames: 
---

# EVT_UDECX_USB_DEVICE_D0_ENTRY callback function


## -description


The USB device emulation class extension (UdeCx) invokes this callback function when it gets a request to bring the virtual USB device out of a low power state to working state.


## -parameters




### -param UdecxWdfDevice [in]

A handle to a framework device object that represents the controller to which the USB device is attached. The client driver initialized this object in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt627990">UdecxWdfDeviceAddUsbDeviceEmulation</a>.


### -param UdecxUsbDevice [in]

A handle to UDE device object. The client driver created this object in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt595959">UdecxUsbDeviceCreate</a>.


## -returns



If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE.




## -remarks



The client driver registered the function in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt627972">UdecxUsbDeviceInitSetStateChangeCallbacks</a> by supplying a function pointer to its implementation.

In the callback implementation, the client driver for the USB device is expected to perform steps to enter working state. 

The power request may be completed asynchronously by returning STATUS_PENDING, and then later completing it by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt627974">UdecxUsbDeviceLinkPowerExitComplete</a> with the actual completion code.





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595911">EVT_UDECX_USB_DEVICE_D0_EXIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt627974">UdecxUsbDeviceLinkPowerExitComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt627982">UdecxUsbDeviceSignalWake</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>
 

 

