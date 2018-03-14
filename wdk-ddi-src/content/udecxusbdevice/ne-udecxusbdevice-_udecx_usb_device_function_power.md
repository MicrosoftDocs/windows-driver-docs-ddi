---
UID: NE:udecxusbdevice._UDECX_USB_DEVICE_FUNCTION_POWER
title: "_UDECX_USB_DEVICE_FUNCTION_POWER"
author: windows-driver-content
description: Defines values for function wake capability of a virtual USB 3.0 device.
old-location: buses\udecx_usb_device_function_power.htm
old-project: usbref
ms.assetid: 7EE6D8AE-E001-4BC9-A617-682202A297E7
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUDECX_USB_DEVICE_FUNCTION_POWER, PUDECX_USB_DEVICE_FUNCTION_POWER, PUDECX_USB_DEVICE_FUNCTION_POWER enumeration pointer [Buses], UDECX_USB_DEVICE_FUNCTION_POWER, UDECX_USB_DEVICE_FUNCTION_POWER enumeration [Buses], UdecxUsbDeviceFunctionNotSuspended, UdecxUsbDeviceFunctionSuspendedCanWake, UdecxUsbDeviceFunctionSuspendedCannotWake, _UDECX_USB_DEVICE_FUNCTION_POWER, buses.udecx_usb_device_function_power, udecxusbdevice/PUDECX_USB_DEVICE_FUNCTION_POWER, udecxusbdevice/UDECX_USB_DEVICE_FUNCTION_POWER, udecxusbdevice/UdecxUsbDeviceFunctionNotSuspended, udecxusbdevice/UdecxUsbDeviceFunctionSuspendedCanWake, udecxusbdevice/UdecxUsbDeviceFunctionSuspendedCannotWake"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: udecxusbdevice.h
req.include-header: Udecx.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	UdecxUsbDevice.h
api_name:
-	UDECX_USB_DEVICE_FUNCTION_POWER
product: Windows
targetos: Windows
req.typenames: UDECX_USB_DEVICE_FUNCTION_POWER, *PUDECX_USB_DEVICE_FUNCTION_POWER
req.product: Windows 10 or later.
---

# _UDECX_USB_DEVICE_FUNCTION_POWER enumeration


## -description


Defines values for function wake capability of a virtual USB 3.0  device.


## -syntax


````
typedef enum _UDECX_USB_DEVICE_FUNCTION_POWER { 
  UdecxUsbDeviceFunctionNotSuspended         = 0,
  UdecxUsbDeviceFunctionSuspendedCannotWake  = ,
  UdecxUsbDeviceFunctionSuspendedCanWake     = 
} UDECX_USB_DEVICE_FUNCTION_POWER, *PUDECX_USB_DEVICE_FUNCTION_POWER;
````


## -enum-fields




### -field UdecxUsbDeviceFunctionNotSuspended

The USB interface cannot enter function suspend. 


### -field UdecxUsbDeviceFunctionSuspendedCannotWake

The USB interface cannot send a wake signal to the host controller.


### -field UdecxUsbDeviceFunctionSuspendedCanWake

The USB interface can send a wake signal to the host controller when the function is in suspend state.


## -see-also

<a href="..\udecxusbdevice\nc-udecxusbdevice-evt_udecx_usb_device_set_function_suspend_and_wake.md">EVT_UDECX_USB_DEVICE_SET_FUNCTION_SUSPEND_AND_WAKE</a>



 

 


