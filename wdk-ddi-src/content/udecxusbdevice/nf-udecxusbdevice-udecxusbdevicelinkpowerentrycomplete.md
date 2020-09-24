---
UID: NF:udecxusbdevice.UdecxUsbDeviceLinkPowerEntryComplete
title: UdecxUsbDeviceLinkPowerEntryComplete function (udecxusbdevice.h)
description: Completes an asynchronous request for bringing the device out of a low power state.
old-location: buses\udecxusbdevicelinkpowerentrycomplete.htm
tech.root: usbref
ms.assetid: 0B8FF9EB-63E5-4532-B13C-CF0FF04D9A53
ms.date: 05/07/2018
keywords: ["UdecxUsbDeviceLinkPowerEntryComplete function"]
ms.keywords: UdecxUsbDeviceLinkPowerEntryComplete, UdecxUsbDeviceLinkPowerEntryComplete function [Buses], buses.udecxusbdevicelinkpowerentrycomplete, udecxusbdevice/UdecxUsbDeviceLinkPowerEntryComplete
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
 - UdecxUsbDeviceLinkPowerEntryComplete
 - udecxusbdevice/UdecxUsbDeviceLinkPowerEntryComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Udecxstub.lib
 - Udecxstub.dll
api_name:
 - UdecxUsbDeviceLinkPowerEntryComplete
---

# UdecxUsbDeviceLinkPowerEntryComplete function


## -description

Completes an asynchronous request for bringing the device out of a low power state.

## -parameters

### -param UdecxUsbDevice 

[in]
A handle to UDE device object. The client driver retrieved this pointer in the previous call to <a href="/windows-hardware/drivers/ddi/udecxusbdevice/nf-udecxusbdevice-udecxusbdevicecreate">UdecxUsbDeviceCreate</a>.

### -param CompletionStatus 

[in]
An appropriate <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS</a> error code that indicates the success or failure of the asynchronous operation.

## -remarks

When the USB device emulation class extension (UdeCx) gets a request to bring the device from low power state and enter working state, it invokes the client driver's implementation of the <a href="/windows-hardware/drivers/ddi/udecxusbdevice/nc-udecxusbdevice-evt_udecx_usb_device_d0_entry">EVT_UDECX_USB_DEVICE_D0_ENTRY</a> callback function. 

After the client driver has performed the necessary steps for bringing the virtual USB device to working state, the driver calls this method to notify the class extension that it has completed the power request.

## -see-also

<a href="/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="/windows-hardware/drivers/ddi/udecxusbdevice/nc-udecxusbdevice-evt_udecx_usb_device_d0_entry">EVT_UDECX_USB_DEVICE_D0_ENTRY</a>



<a href="/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>