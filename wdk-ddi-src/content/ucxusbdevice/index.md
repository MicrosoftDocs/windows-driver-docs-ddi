---
UID: NA:ucxusbdevice
ms.assetid: 2cf71389-08f1-3c73-b478-7efa6045e05e
ms.author: windowsdriverdev
ms.date: 03/13/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ucxusbdevice.h header



This header is used by Universal Serial Bus(USB). For more information, see
- [Universal Serial Bus(USB)](../_usbref/index.md)

Ucxusbdevice.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [UCX_USBDEVICE_EVENT_CALLBACKS_INIT function](nf-ucxusbdevice-ucx_usbdevice_event_callbacks_init.md) | Initializes a UCX_USBDEVICE_EVENT_CALLBACKS structure with the function pointers to client driver's callback functions. |
| [UcxUsbDeviceCreate function](nf-ucxusbdevice-ucxusbdevicecreate.md) | Creates a USB device object on the specified controller. |
| [UcxUsbDeviceInitSetEventCallbacks function](nf-ucxusbdevice-ucxusbdeviceinitseteventcallbacks.md) | Initializes a UCXUSBDEVICE_INIT structure with client driver's event callback functions. |
| [UcxUsbDeviceRemoteWakeNotification function](nf-ucxusbdevice-ucxusbdeviceremotewakenotification.md) | Notifies UCX that a remote wake signal from the device is received. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EVT_UCX_USBDEVICE_ADDRESS callback](nc-ucxusbdevice-evt_ucx_usbdevice_address.md) | The client driver's implementation that UCX calls to address the USB device. |
| [EVT_UCX_USBDEVICE_DEFAULT_ENDPOINT_ADD callback](nc-ucxusbdevice-evt_ucx_usbdevice_default_endpoint_add.md) | The client driver's implementation that UCX calls to add a new default endpoint for a USB device. |
| [EVT_UCX_USBDEVICE_DISABLE callback](nc-ucxusbdevice-evt_ucx_usbdevice_disable.md) | The client driver's implementation that UCX calls to release controller resources associated with the device and its default endpoint. |
| [EVT_UCX_USBDEVICE_ENABLE callback](nc-ucxusbdevice-evt_ucx_usbdevice_enable.md) | The client driver's implementation that UCX calls to program information about the device and its default control endpoint into the controller. |
| [EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE callback](nc-ucxusbdevice-evt_ucx_usbdevice_endpoints_configure.md) | The client driver's implementation that UCX calls to configure endpoints in the controller. |
| [EVT_UCX_USBDEVICE_ENDPOINT_ADD callback](nc-ucxusbdevice-evt_ucx_usbdevice_endpoint_add.md) | The client driver's implementation that UCX calls to add a new endpoint for a USB device. |
| [EVT_UCX_USBDEVICE_GET_CHARACTERISTIC callback](nc-ucxusbdevice-evt_ucx_usbdevice_get_characteristic.md) | UCX invokes this callback to retrieve the device characteristics. |
| [EVT_UCX_USBDEVICE_HUB_INFO callback](nc-ucxusbdevice-evt_ucx_usbdevice_hub_info.md) | The client driver's implementation that UCX calls to retrieve hub properties. |
| [EVT_UCX_USBDEVICE_RESET callback](nc-ucxusbdevice-evt_ucx_usbdevice_reset.md) | The client driver's implementation that UCX calls when the port to which the device is attached is reset. |
| [EVT_UCX_USBDEVICE_RESUME callback](nc-ucxusbdevice-evt_ucx_usbdevice_resume.md) | UCX invokes this callback function to resume a device from suspend state. |
| [EVT_UCX_USBDEVICE_SUSPEND callback](nc-ucxusbdevice-evt_ucx_usbdevice_suspend.md) | UCX invokes this callback function to send a device suspend state. |
| [EVT_UCX_USBDEVICE_UPDATE callback](nc-ucxusbdevice-evt_ucx_usbdevice_update.md) | The client driver's implementation that UCX calls to update device properties. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_ADDRESS0_OWNERSHIP_ACQUIRE structure](ns-ucxusbdevice-_address0_ownership_acquire.md) | Contains parameters for configuring the device. |
| [_UCXUSBDEVICE_INFO structure](ns-ucxusbdevice-_ucxusbdevice_info.md) | Contains information about the USB device. This structure is passed by UCX in the EVT_UCX_CONTROLLER_USBDEVICE_ADD event callback function. |
| [_UCX_USBDEVICE_CHARACTERISTIC structure](ns-ucxusbdevice-_ucx_usbdevice_characteristic.md) | Stores the characteristics of an device. |
| [_UCX_USBDEVICE_CHARACTERISTIC_PATH_DELAY structure](ns-ucxusbdevice-_ucx_usbdevice_characteristic_path_delay.md) | Stores the isochronous transfer path delay values. |
| [_UCX_USBDEVICE_EVENT_CALLBACKS structure](ns-ucxusbdevice-_ucx_usbdevice_event_callbacks.md) | This structure provides a list of UCX USB device event callback functions. |
| [_USBDEVICE_ABORTIO structure](ns-ucxusbdevice-_usbdevice_abortio.md) | Contains a handle for the Universal Serial Bus (USB) hub or device for which to abort data transfers. |
| [_USBDEVICE_ADDRESS structure](ns-ucxusbdevice-_usbdevice_address.md) | Contains parameters for a request to transition the specified device to the Addressed state. This structure is passed by UCX in request parameters (Parameters.Others.Arg1) of a framework request object of the EVT_UCX_USBDEVICE_ADDRESS callback function. |
| [_USBDEVICE_DISABLE structure](ns-ucxusbdevice-_usbdevice_disable.md) | Contains parameters for a request to disable the specified device. This structure is passed by UCX in request parameters (Parameters.Others.Arg1) of a framework request object of the EVT_UCX_USBDEVICE_DISABLE callback function. |
| [_USBDEVICE_ENABLE structure](ns-ucxusbdevice-_usbdevice_enable.md) | Contains parameters for a request to enable the specified device. This structure is passed by UCX in request parameters (Parameters.Others.Arg1) of a framework request object of the EVT_UCX_USBDEVICE_ENABLE callback function. |
| [_USBDEVICE_ENABLE_FAILURE_FLAGS structure](ns-ucxusbdevice-_usbdevice_enable_failure_flags.md) | The flags that are set by the client driver in the EVT_UCX_USBDEVICE_ENABLE callback function. Indicate errors, if any, that might have occurred while enabling the device. |
| [_USBDEVICE_HUB_INFO structure](ns-ucxusbdevice-_usbdevice_hub_info.md) | Contains parameters for a request to get information about the specified hub. This structure is passed by UCX in request parameters (Parameters.Others.Arg1) of a framework request object of the EVT_UCX_USBDEVICE_HUB_INFO callback function. |
| [_USBDEVICE_MGMT_HEADER structure](ns-ucxusbdevice-_usbdevice_mgmt_header.md) | This structure provides a handle for the Universal Serial Bus (USB) hub or device physically connected to the bus. |
| [_USBDEVICE_PURGEIO structure](ns-ucxusbdevice-_usbdevice_purgeio.md) | The USBDEVICE_PURGEIO structure contains the handle for the Universal Serial Bus (USB) hub or device to purge I/O for. |
| [_USBDEVICE_RESET structure](ns-ucxusbdevice-_usbdevice_reset.md) | Contains parameters for a request to reset the specified device. This structure is passed by UCX in request parameters (Parameters.Others.Arg1) of a framework request object of the EVT_UCX_USBDEVICE_RESET callback function. |
| [_USBDEVICE_STARTIO structure](ns-ucxusbdevice-_usbdevice_startio.md) | Contains a handle for the Universal Serial Bus (USB) hub or device on which to start data transfer. |
| [_USBDEVICE_TREE_PURGEIO structure](ns-ucxusbdevice-_usbdevice_tree_purgeio.md) | This structure provides the handle for the Universal Serial Bus (USB) device tree to purge I/O for. |
| [_USBDEVICE_UPDATE structure](ns-ucxusbdevice-_usbdevice_update.md) | Passed by UCX to update the specified device. This structure is in the request parameters (Parameters.Others.Arg1) of a framework request object passed in the EVT_UCX_USBDEVICE_UPDATE callback function. |
| [_USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS structure](ns-ucxusbdevice-_usbdevice_update_20_hardware_lpm_parameters.md) | Contains parameters for a request to update USB 2.0 link power management (LPM). UCX passes this structure in the EVT_UCX_USBDEVICE_UPDATE callback function. |
| [_USBDEVICE_UPDATE_FAILURE_FLAGS structure](ns-ucxusbdevice-_usbdevice_update_failure_flags.md) | The flags that are set by the client driver in the EVT_UCX_USBDEVICE_UPDATE callback function. Indicate errors, if any, that might have occurred while updating the device. |
| [_USBDEVICE_UPDATE_FLAGS structure](ns-ucxusbdevice-_usbdevice_update_flags.md) | Contains request flags set by UCX that is passed in the USBDEVICE_UPDATE structure when UCX invokes the client driver's EVT_UCX_USBDEVICE_UPDATE callback function. |
| [_USB_DEVICE_PORT_PATH structure](ns-ucxusbdevice-_usb_device_port_path.md) | Contains the port path of a USB device. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_UCX_USBDEVICE_CHARACTERISTIC_TYPE enumeration](ne-ucxusbdevice-_ucx_usbdevice_characteristic_type.md) | Defines values that indicates the type of device characteristic. |
