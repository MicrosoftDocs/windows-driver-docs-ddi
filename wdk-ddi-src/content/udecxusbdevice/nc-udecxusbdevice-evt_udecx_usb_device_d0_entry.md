---
UID: NC:udecxusbdevice.EVT_UDECX_USB_DEVICE_D0_ENTRY
title: EVT_UDECX_USB_DEVICE_D0_ENTRY (udecxusbdevice.h)
description: The USB device emulation class extension (UdeCx) invokes this callback function when it gets a request to bring the virtual USB device out of a low power state to working state.
old-location: buses\evt_udecx_usb_device_d0_entry.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["EVT_UDECX_USB_DEVICE_D0_ENTRY callback function"]
ms.keywords: EVT_UDECX_USB_DEVICE_D0_ENTRY, EVT_UDECX_USB_DEVICE_D0_ENTRY callback, EvtUsbDeviceLinkPowerEntry, EvtUsbDeviceLinkPowerEntry callback function [Buses], buses.evt_udecx_usb_device_d0_entry, udecxusbdevice/EvtUsbDeviceLinkPowerEntry
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
targetos: Windows
req.typenames: 
f1_keywords:
 - EVT_UDECX_USB_DEVICE_D0_ENTRY
 - udecxusbdevice/EVT_UDECX_USB_DEVICE_D0_ENTRY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - udecxusbdevice.h
api_name:
 - EVT_UDECX_USB_DEVICE_D0_ENTRY
---

# EVT_UDECX_USB_DEVICE_D0_ENTRY callback function


## -description

The USB device emulation class extension (UdeCx) invokes this callback function when it gets a request to bring the virtual USB device out of a low power state to working state.

## -parameters

### -param UdecxWdfDevice 

[in]
A handle to a framework device object that represents the controller to which the USB device is attached. The client driver initialized this object in a previous call to <a href="/windows-hardware/drivers/ddi/udecxwdfdevice/nf-udecxwdfdevice-udecxwdfdeviceaddusbdeviceemulation">UdecxWdfDeviceAddUsbDeviceEmulation</a>.

### -param UdecxUsbDevice 

[in]
A handle to UDE device object. The client driver created this object in a previous call to <a href="/windows-hardware/drivers/ddi/udecxusbdevice/nf-udecxusbdevice-udecxusbdevicecreate">UdecxUsbDeviceCreate</a>.

## -returns

If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE.

## -remarks

The client driver registered the function in a previous call to <a href="/windows-hardware/drivers/ddi/udecxusbdevice/nf-udecxusbdevice-udecxusbdeviceinitsetstatechangecallbacks">UdecxUsbDeviceInitSetStateChangeCallbacks</a> by supplying a function pointer to its implementation.

In the callback implementation, the client driver for the USB device is expected to perform steps to enter working state. 

The power request may be completed asynchronously by returning STATUS_PENDING, and then later completing it by calling <a href="/windows-hardware/drivers/ddi/udecxusbdevice/nf-udecxusbdevice-udecxusbdevicelinkpowerexitcomplete">UdecxUsbDeviceLinkPowerExitComplete</a> with the actual completion code.

## -see-also

<a href="/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="/windows-hardware/drivers/ddi/udecxusbdevice/nc-udecxusbdevice-evt_udecx_usb_device_d0_exit">EVT_UDECX_USB_DEVICE_D0_EXIT</a>



<a href="/windows-hardware/drivers/ddi/udecxusbdevice/nf-udecxusbdevice-udecxusbdevicelinkpowerexitcomplete">UdecxUsbDeviceLinkPowerExitComplete</a>



<a href="/windows-hardware/drivers/ddi/udecxusbdevice/nf-udecxusbdevice-udecxusbdevicesignalwake">UdecxUsbDeviceSignalWake</a>



<a href="/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>

