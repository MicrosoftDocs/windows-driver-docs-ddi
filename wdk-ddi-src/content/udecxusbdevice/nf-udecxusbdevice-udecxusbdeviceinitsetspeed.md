---
UID: NF:udecxusbdevice.UdecxUsbDeviceInitSetSpeed
title: UdecxUsbDeviceInitSetSpeed function
author: windows-driver-content
description: Sets the USB speed of the virtual USB device to create.
old-location: buses\udecxusbdeviceinitsetspeed.htm
old-project: usbref
ms.assetid: D7EF9B82-5156-4F27-AA52-94C113C81D3A
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UdecxUsbDeviceInitSetSpeed, UdecxUsbDeviceInitSetSpeed function [Buses], buses.udecxusbdeviceinitsetspeed, udecxusbdevice/UdecxUsbDeviceInitSetSpeed
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Udecxstub.lib
-	Udecxstub.dll
api_name:
-	UdecxUsbDeviceInitSetSpeed
product: Windows
targetos: Windows
req.typenames: UDECX_USB_DEVICE_WAKE_SETTING, *PUDECX_USB_DEVICE_WAKE_SETTING
req.product: Windows 10 or later.
---

# UdecxUsbDeviceInitSetSpeed function


## -description


Sets the USB speed of the virtual USB device to create. 


## -syntax


````
FORCEINLINE void UdecxUsbDeviceInitSetSpeed(
  _Inout_ PUDECXUSBDEVICE_INIT   UdecxUsbDeviceInit,
  _In_    UDECX_USB_DEVICE_SPEED UsbDeviceSpeed
);
````


## -parameters




### -param UdecxUsbDeviceInit [in, out]

A pointer to a WDF-allocated structure that contains initialization parameters for the virtual USB device.  The client driver retrieved this pointer in the previous call to <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdeviceinitallocate.md">UdecxUsbDeviceInitAllocate</a>. 


### -param UsbDeviceSpeed [in]

A <a href="..\udecxusbdevice\ne-udecxusbdevice-_udecx_usb_device_speed.md">UDECX_USB_DEVICE_SPEED</a>-type value that indicates the USB speed to set.


## -returns



This function does not return a value.




## -remarks



After the client driver sets the USB speed of the device, it only operates in that speed. The speed also determines the kind of port to which the device can connect. For example, a USB SuperSpeed device cannot connect to a USB 2.0 port.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UdecxUsbDeviceInitSetSpeed function%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

