---
UID: NF:udecxusbdevice.UdecxUsbDeviceSignalWake
title: UdecxUsbDeviceSignalWake function (udecxusbdevice.h)
description: Initiates wake up from a low link power state for a virtual USB 2.0 device.
old-location: buses\udecxusbdevicesignalwake.htm
tech.root: usbref
ms.assetid: BF8C1D85-6C88-4F4C-ADDB-CCE603D420F2
ms.date: 05/07/2018
keywords: ["UdecxUsbDeviceSignalWake function"]
ms.keywords: UdecxUsbDeviceSignalWake, UdecxUsbDeviceSignalWake function [Buses], buses.udecxusbdevicesignalwake, udecxusbdevice/UdecxUsbDeviceSignalWake
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
 - UdecxUsbDeviceSignalWake
 - udecxusbdevice/UdecxUsbDeviceSignalWake
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Udecxstub.lib
 - Udecxstub.dll
api_name:
 - UdecxUsbDeviceSignalWake
---

# UdecxUsbDeviceSignalWake function


## -description

Initiates wake up from a low link power state for a virtual USB 2.0 device.

## -parameters

### -param UdecxUsbDevice 

[in]
A handle to UDE device object. The client driver retrieved this pointer in the previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbdevice/nf-udecxusbdevice-udecxusbdevicecreate">UdecxUsbDeviceCreate</a>.

## -remarks

The client driver for the device must have enabled wake capability in the most recent <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbdevice/nc-udecxusbdevice-evt_udecx_usb_device_d0_exit">EVT_UDECX_USB_DEVICE_D0_EXIT</a> call.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbdevice/nc-udecxusbdevice-evt_udecx_usb_device_d0_exit">EVT_UDECX_USB_DEVICE_D0_EXIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>

