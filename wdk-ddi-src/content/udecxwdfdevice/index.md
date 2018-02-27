---
UID: NA:udecxwdfdevice
ms.assetid: d0a5a6e1-0a40-3c57-8704-6ba20faac4d9
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Udecxwdfdevice.h header



This header is used by Universal Serial Bus(USB). For more information, see
- [Universal Serial Bus(USB)](../_usbref/index.md)

Udecxwdfdevice.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [UDECX_WDF_DEVICE_CONFIG_INIT function](nf-udecxwdfdevice-udecx_wdf_device_config_init.md) | Initializes a UDECX_WDF_DEVICE_CONFIG structure. |
| [UdecxInitializeWdfDeviceInit function](nf-udecxwdfdevice-udecxinitializewdfdeviceinit.md) | Initializes device initialization operations when the Plug and Play (PnP) manager reports the existence of a device. |
| [UdecxWdfDeviceAddUsbDeviceEmulation function](nf-udecxwdfdevice-udecxwdfdeviceaddusbdeviceemulation.md) | Initializes a framework device object to support operations related to a host controller and a virtual USB device attached to the controller. |
| [UdecxWdfDeviceResetComplete function](nf-udecxwdfdevice-udecxwdfdeviceresetcomplete.md) | Informs the USB device emulation class extension (UdeCx) that the reset operation on the specified controller has competed. |
| [UdecxWdfDeviceTryHandleUserIoctl function](nf-udecxwdfdevice-udecxwdfdevicetryhandleuserioctl.md) | Attempts to handle an IOCTL request sent by a user-mode software. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EVT_UDECX_WDF_DEVICE_QUERY_USB_CAPABILITY callback](nc-udecxwdfdevice-evt_udecx_wdf_device_query_usb_capability.md) | The UDE client driver's implementation to determine the capabilities that are supported by the emulated USB host controller. |
| [EVT_UDECX_WDF_DEVICE_RESET callback](nc-udecxwdfdevice-evt_udecx_wdf_device_reset.md) | The UDE client driver's implementation to reset the emulated host controller or the devices attached to it. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_UDECX_WDF_DEVICE_CONFIG structure](ns-udecxwdfdevice-_udecx_wdf_device_config.md) | Contains pointers to event callback functions implemented by the UDE client driver for a USB host controller. Initialize this structure by calling UDECX_WDF_DEVICE_CONFIG_INIT. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_UDECX_WDF_DEVICE_RESET_ACTION enumeration](ne-udecxwdfdevice-_udecx_wdf_device_reset_action.md) | Defines values that indicate the types of reset operation supported by an emulated USB host controller. |
