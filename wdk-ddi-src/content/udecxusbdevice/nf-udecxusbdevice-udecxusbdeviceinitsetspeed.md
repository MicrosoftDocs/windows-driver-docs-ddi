---
UID: NF:udecxusbdevice.UdecxUsbDeviceInitSetSpeed
title: UdecxUsbDeviceInitSetSpeed function (udecxusbdevice.h)
description: Sets the USB speed of the virtual USB device to create.
old-location: buses\udecxusbdeviceinitsetspeed.htm
tech.root: usbref
ms.assetid: D7EF9B82-5156-4F27-AA52-94C113C81D3A
ms.date: 05/07/2018
ms.keywords: UdecxUsbDeviceInitSetSpeed, UdecxUsbDeviceInitSetSpeed function [Buses], buses.udecxusbdeviceinitsetspeed, udecxusbdevice/UdecxUsbDeviceInitSetSpeed
ms.topic: function
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
req.lib: Udecxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Udecxstub.lib
- Udecxstub.dll
api_name:
- UdecxUsbDeviceInitSetSpeed
product:
- Windows
targetos: Windows
req.typenames: 
---

# UdecxUsbDeviceInitSetSpeed function


## -description


Sets the USB speed of the virtual USB device to create. 


## -parameters




### -param UdecxUsbDeviceInit [in, out]

A pointer to a WDF-allocated structure that contains initialization parameters for the virtual USB device.  The client driver retrieved this pointer in the previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/udecxusbdevice/nf-udecxusbdevice-udecxusbdeviceinitallocate">UdecxUsbDeviceInitAllocate</a>. 


### -param UsbDeviceSpeed [in]

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/udecxusbdevice/ne-udecxusbdevice-_udecx_usb_device_speed">UDECX_USB_DEVICE_SPEED</a>-type value that indicates the USB speed to set.


## -returns



This function does not return a value.




## -remarks



After the client driver sets the USB speed of the device, it only operates in that speed. The speed also determines the kind of port to which the device can connect. For example, a USB SuperSpeed device cannot connect to a USB 2.0 port.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>
 

 

