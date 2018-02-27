---
UID: NA:udecxusbdevice
ms.assetid: bdf4ca1b-17bf-3c92-8ed6-296d65ebf2cc
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Udecxusbdevice.h header



This header is used by Universal Serial Bus(USB). For more information, see
- [Universal Serial Bus(USB)](../_usbref/index.md)

Udecxusbdevice.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [UDECX_USB_DEVICE_CALLBACKS_INIT function](nf-udecxusbdevice-udecx_usb_device_callbacks_init.md) | Initializes a UDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS structure before a UdecxUsbDeviceCreate call. |
| [UDECX_USB_DEVICE_PLUG_IN_OPTIONS_INIT function](nf-udecxusbdevice-udecx_usb_device_plug_in_options_init.md) | Initializes a UDECX_USB_DEVICE_PLUG_IN_OPTIONS structure. |
| [UdecxUsbDeviceCreate function](nf-udecxusbdevice-udecxusbdevicecreate.md) | Creates a USB Device Emulation (UDE) device object. |
| [UdecxUsbDeviceInitAddDescriptor function](nf-udecxusbdevice-udecxusbdeviceinitadddescriptor.md) | Adds a USB descriptor to the initialization parameters used to create a virtual USB device. |
| [UdecxUsbDeviceInitAddDescriptorWithIndex function](nf-udecxusbdevice-udecxusbdeviceinitadddescriptorwithindex.md) | Adds a USB descriptor to the initialization parameters used to create a virtual USB device. |
| [UdecxUsbDeviceInitAddStringDescriptor function](nf-udecxusbdevice-udecxusbdeviceinitaddstringdescriptor.md) | Adds a USB string descriptor to the initialization parameters used to create a virtual USB device. |
| [UdecxUsbDeviceInitAddStringDescriptorRaw function](nf-udecxusbdevice-udecxusbdeviceinitaddstringdescriptorraw.md) | Adds a USB string descriptor to the initialization parameters used to create a virtual USB device. |
| [UdecxUsbDeviceInitAllocate function](nf-udecxusbdevice-udecxusbdeviceinitallocate.md) | Allocates memory for a UDECXUSBDEVICE_INIT structure that is used to initialize a virtual USB device. |
| [UdecxUsbDeviceInitFree function](nf-udecxusbdevice-udecxusbdeviceinitfree.md) | Releases the resources that were allocated by the UdecxUsbDeviceInitAllocate call. |
| [UdecxUsbDeviceInitSetEndpointsType function](nf-udecxusbdevice-udecxusbdeviceinitsetendpointstype.md) | Indicates the type of endpoint (simple or dynamic) in the initialization parameters that the client driver uses to create the virtual USB device. |
| [UdecxUsbDeviceInitSetSpeed function](nf-udecxusbdevice-udecxusbdeviceinitsetspeed.md) | Sets the USB speed of the virtual USB device to create. |
| [UdecxUsbDeviceInitSetStateChangeCallbacks function](nf-udecxusbdevice-udecxusbdeviceinitsetstatechangecallbacks.md) | Initializes a WDF-allocated structure with pointers to callback functions. |
| [UdecxUsbDeviceLinkPowerEntryComplete function](nf-udecxusbdevice-udecxusbdevicelinkpowerentrycomplete.md) | Completes an asynchronous request for bringing the device out of a low power state. |
| [UdecxUsbDeviceLinkPowerExitComplete function](nf-udecxusbdevice-udecxusbdevicelinkpowerexitcomplete.md) | Completes an asynchronous request for sending the device to a low power state. |
| [UdecxUsbDevicePlugIn function](nf-udecxusbdevice-udecxusbdeviceplugin.md) | Notifies the USB device emulation class extension (UdeCx) that the USB device has been plugged in the specified port. |
| [UdecxUsbDevicePlugOutAndDelete function](nf-udecxusbdevice-udecxusbdeviceplugoutanddelete.md) | Disconnects the virtual USB device. |
| [UdecxUsbDeviceSetFunctionSuspendAndWakeComplete function](nf-udecxusbdevice-udecxusbdevicesetfunctionsuspendandwakecomplete.md) | Completes an asynchronous request for changing the power state of a particular function of a virtual USB 3.0 device. |
| [UdecxUsbDeviceSignalFunctionWake function](nf-udecxusbdevice-udecxusbdevicesignalfunctionwake.md) | Initiates wake up of the specified function from a low power state. This applies to virtual USB 3.0 devices. |
| [UdecxUsbDeviceSignalWake function](nf-udecxusbdevice-udecxusbdevicesignalwake.md) | Initiates wake up from a low link power state for a virtual USB 2.0 device. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EVT_UDECX_USB_DEVICE_D0_ENTRY callback](nc-udecxusbdevice-evt_udecx_usb_device_d0_entry.md) | The USB device emulation class extension (UdeCx) invokes this callback function when it gets a request to bring the virtual USB device out of a low power state to working state. |
| [EVT_UDECX_USB_DEVICE_D0_EXIT callback](nc-udecxusbdevice-evt_udecx_usb_device_d0_exit.md) | The USB device emulation class extension (UdeCx) invokes this callback function when it gets a request to send the virtual USB device to a low power state. |
| [EVT_UDECX_USB_DEVICE_DEFAULT_ENDPOINT_ADD callback](nc-udecxusbdevice-evt_udecx_usb_device_default_endpoint_add.md) | The USB device emulation class extension (UdeCx) invokes this callback function to request the client driver to create the default control endpoint on the virtual USB device. |
| [EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE callback](nc-udecxusbdevice-evt_udecx_usb_device_endpoints_configure.md) | The USB device emulation class extension (UdeCx) invokes this callback function to change the configuration by selecting an alternate setting, disabling current endpoints, or adding dynamic endpoints. |
| [EVT_UDECX_USB_DEVICE_ENDPOINT_ADD callback](nc-udecxusbdevice-evt_udecx_usb_device_endpoint_add.md) | The USB device emulation class extension (UdeCx) invokes this callback function to request the client driver to create a dynamic endpoint on the virtual USB device. |
| [EVT_UDECX_USB_DEVICE_SET_FUNCTION_SUSPEND_AND_WAKE callback](nc-udecxusbdevice-evt_udecx_usb_device_set_function_suspend_and_wake.md) | The USB device emulation class extension (UdeCx) invokes this callback function when it gets a request to change the function state of the specified interface of the virtual USB 3.0 device. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_UDECX_ENDPOINTS_CONFIGURE_PARAMS structure](ns-udecxusbdevice-_udecx_endpoints_configure_params.md) | Contains the configuration options specified by USB device emulation class extension (UdeCx) to the client driver when the class extension invokes EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE. |
| [_UDECX_USB_DEVICE_PLUG_IN_OPTIONS structure](ns-udecxusbdevice-_udecx_usb_device_plug_in_options.md) | Contains the port numbers to which a virtual USB device is connected. Initialize this structure by calling the UDECX_USB_DEVICE_PLUG_IN_OPTIONS_INIT method. |
| [_UDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS structure](ns-udecxusbdevice-_udecx_usb_device_state_change_callbacks.md) | Initializes a UDECX_USB_DEVICE_STATE_CHANGE_CALLBACKS structure with pointers to callback functions that are implemented by a UDE client for a virtual USB device. |
| [_UDECX_USB_ENDPOINT_INIT_AND_METADATA structure](ns-udecxusbdevice-_udecx_usb_endpoint_init_and_metadata.md) | Contains the descriptors supported by an endpoint of a virtual USB device. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_UDECX_ENDPOINTS_CONFIGURE_TYPE enumeration](ne-udecxusbdevice-_udecx_endpoints_configure_type.md) | Defines values for endpoint configuration options. |
| [_UDECX_ENDPOINT_TYPE enumeration](ne-udecxusbdevice-_udecx_endpoint_type.md) | Defines values for endpoint types supported by a virtual USB device. |
| [_UDECX_USB_DEVICE_FUNCTION_POWER enumeration](ne-udecxusbdevice-_udecx_usb_device_function_power.md) | Defines values for function wake capability of a virtual USB 3.0 device. |
| [_UDECX_USB_DEVICE_SPEED enumeration](ne-udecxusbdevice-_udecx_usb_device_speed.md) | Defines values for USB device speeds. |
| [_UDECX_USB_DEVICE_WAKE_SETTING enumeration](ne-udecxusbdevice-_udecx_usb_device_wake_setting.md) | Defines values for remote wake capability of a virtual USB device. |
