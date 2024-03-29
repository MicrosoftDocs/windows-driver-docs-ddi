---
UID: NF:udecxusbdevice.UdecxUsbDeviceInitSetStateChangeCallbacks
title: UdecxUsbDeviceInitSetStateChangeCallbacks function (udecxusbdevice.h)
description: Initializes a WDF-allocated structure with pointers to callback functions.
old-location: buses\udecxusbdeviceinitsetstatechangecallbacks.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UdecxUsbDeviceInitSetStateChangeCallbacks function"]
ms.keywords: UdecxUsbDeviceInitSetStateChangeCallbacks, UdecxUsbDeviceInitSetStateChangeCallbacks function [Buses], buses.udecxusbdeviceinitsetstatechangecallbacks, udecxusbdevice/UdecxUsbDeviceInitSetStateChangeCallbacks
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
targetos: Windows
req.typenames: 
f1_keywords:
 - UdecxUsbDeviceInitSetStateChangeCallbacks
 - udecxusbdevice/UdecxUsbDeviceInitSetStateChangeCallbacks
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Udecxstub.lib
 - Udecxstub.dll
api_name:
 - UdecxUsbDeviceInitSetStateChangeCallbacks
---

# UdecxUsbDeviceInitSetStateChangeCallbacks function


## -description

Initializes a WDF-allocated structure with pointers to callback functions.

## -parameters

### -param UdecxUsbDeviceInit [in, out]


A pointer to a WDF-allocated structure that contains initialization parameters for the virtual USB device.  The client driver retrieved this pointer in the previous call to <a href="/windows-hardware/drivers/ddi/udecxusbdevice/nf-udecxusbdevice-udecxusbdeviceinitallocate">UdecxUsbDeviceInitAllocate</a>.

### -param Callbacks [in]


A pointer to a <a href="/windows-hardware/drivers/ddi/udecxusbdevice/ns-udecxusbdevice-_udecx_usb_device_state_change_callbacks">UDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS</a> structure that contains pointers to callback functions implemented by the client driver.

## -see-also

<a href="/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="/windows-hardware/drivers/ddi/udecxusbdevice/nf-udecxusbdevice-udecxusbdeviceinitallocate">UdecxUsbDeviceInitAllocate</a>



<a href="/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>
