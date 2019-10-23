---
UID: NE:udecxusbdevice._UDECX_USB_DEVICE_WAKE_SETTING
title: _UDECX_USB_DEVICE_WAKE_SETTING (udecxusbdevice.h)
description: Defines values for remote wake capability of a virtual USB device.
old-location: buses\udecx_usb_device_wake_setting.htm
tech.root: usbref
ms.assetid: 0CA3B49C-B2A7-497D-A97B-4AC845074BEC
ms.date: 05/07/2018
ms.keywords: "*PUDECX_USB_DEVICE_WAKE_SETTING, PUDECX_USB_DEVICE_WAKE_SETTING, PUDECX_USB_DEVICE_WAKE_SETTING enumeration pointer [Buses], UDECX_USB_DEVICE_WAKE_SETTING, UDECX_USB_DEVICE_WAKE_SETTING enumeration [Buses], UdecxUsbDeviceWakeDisabled, UdecxUsbDeviceWakeEnabled, UdecxUsbDeviceWakeNotApplicable, _UDECX_USB_DEVICE_WAKE_SETTING, buses.udecx_usb_device_wake_setting, udecxusbdevice/PUDECX_USB_DEVICE_WAKE_SETTING, udecxusbdevice/UDECX_USB_DEVICE_WAKE_SETTING, udecxusbdevice/UdecxUsbDeviceWakeDisabled, udecxusbdevice/UdecxUsbDeviceWakeEnabled, udecxusbdevice/UdecxUsbDeviceWakeNotApplicable"
ms.topic: enum
f1_keywords:
 - "udecxusbdevice/UDECX_USB_DEVICE_WAKE_SETTING"
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
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- UdecxUsbDevice.h
api_name:
- UDECX_USB_DEVICE_WAKE_SETTING
product:
- Windows
targetos: Windows
req.typenames: UDECX_USB_DEVICE_WAKE_SETTING, *PUDECX_USB_DEVICE_WAKE_SETTING
---

# _UDECX_USB_DEVICE_WAKE_SETTING enumeration


## -description


Defines values for remote wake capability of a virtual USB device.


## -enum-fields




### -field UdecxUsbDeviceWakeDisabled

The USB device cannot send a wake signal to the host controller.


### -field UdecxUsbDeviceWakeEnabled

The USB device can send a wake signal to the host controller.


### -field UdecxUsbDeviceWakeNotApplicable

This value is used only if the USB device is a SuperSpeed device.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/udecxusbdevice/nc-udecxusbdevice-evt_udecx_usb_device_d0_exit">EVT_UDECX_USB_DEVICE_D0_EXIT</a>
 

 

