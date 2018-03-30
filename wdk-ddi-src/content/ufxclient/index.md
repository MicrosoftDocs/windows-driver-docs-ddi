---
UID: NA:ufxclient
ms.assetid: a102bd53-90d1-3f5d-ad42-1dedbc9a7679
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ufxclient.h header



This header is used by Universal Serial Bus(USB). For more information, see
- [Universal Serial Bus(USB)](../_usbref/index.md)

Ufxclient.h contain these programming interfaces:


## Functions

| Title   | Description   |
| ---- |:---- |
| [UFX_DEVICE_CALLBACKS_INIT function](nf-ufxclient-ufx_device_callbacks_init.md) | The UFX_DEVICE_CALLBACKS_INIT macro initializes the UFX_DEVICE_CALLBACKS structure. |
| [UFX_DEVICE_CAPABILITIES_INIT function](nf-ufxclient-ufx_device_capabilities_init.md) | The UFX_DEVICE_CAPABILITIES_INIT macro the initializes the UFX_DEVICE_CAPABILITIES structure. |
| [UFX_ENDPOINT_CALLBACKS_INIT function](nf-ufxclient-ufx_endpoint_callbacks_init.md) | The UFX_ENDPOINT_CALLBACKS_INIT macro initializes the UFX_ENDPOINT_CALLBACKS structure. |
| [UfxDeviceCreate function](nf-ufxclient-ufxdevicecreate.md) | Creates a UFX device object, registers event callback routines, and specifies capabilities specific to the controller. |
| [UfxDeviceEventComplete function](nf-ufxclient-ufxdeviceeventcomplete.md) | Informs UFX that the client driver has completed processing a UFX callback function. |
| [UfxDeviceIoControl function](nf-ufxclient-ufxdeviceiocontrol.md) | Passes non-internal IOCTLs from user-mode to UFX. |
| [UfxDeviceIoInternalControl function](nf-ufxclient-ufxdeviceiointernalcontrol.md) | Passes kernel mode IOCTLs to UFX. |
| [UfxDeviceNotifyAttach function](nf-ufxclient-ufxdevicenotifyattach.md) | Notifies UFX that the device's USB cable has been attached. |
| [UfxDeviceNotifyDetach function](nf-ufxclient-ufxdevicenotifydetach.md) | Notifies UFX that the device's USB cable has been detached. |
| [UfxDeviceNotifyHardwareFailure function](nf-ufxclient-ufxdevicenotifyhardwarefailure.md) | Notifies UFX about a non-recoverable hardware failure in the controller. |
| [UfxDeviceNotifyHardwareReady function](nf-ufxclient-ufxdevicenotifyhardwareready.md) | Notifies UFX that the hardware is ready. |
| [UfxDeviceNotifyReset function](nf-ufxclient-ufxdevicenotifyreset.md) | Notifies UFX about a USB bus reset event. |
| [UfxDeviceNotifyResume function](nf-ufxclient-ufxdevicenotifyresume.md) | Notifies UFX about a USB bus resume event. |
| [UfxDeviceNotifySuspend function](nf-ufxclient-ufxdevicenotifysuspend.md) | Notifies UFX about a USB bus suspend event. |
| [UfxDevicePortDetectComplete function](nf-ufxclient-ufxdeviceportdetectcomplete.md) | Notifies UFX about the port type that was detected. |
| [UfxDevicePortDetectCompleteEx function](nf-ufxclient-ufxdeviceportdetectcompleteex.md) | Notifies UFX about the port type that was detected, and optionally requests an action. |
| [UfxDeviceProprietaryChargerDetectComplete function](nf-ufxclient-ufxdeviceproprietarychargerdetectcomplete.md) | Notifies UFX about a detected proprietary port/charger type. |
| [UfxEndpointCreate function](nf-ufxclient-ufxendpointcreate.md) | Creates an endpoint object. |
| [UfxEndpointGetCommandQueue function](nf-ufxclient-ufxendpointgetcommandqueue.md) | Returns the command queue previously created by UfxEndpointCreate. |
| [UfxEndpointGetTransferQueue function](nf-ufxclient-ufxendpointgettransferqueue.md) | Returns the transfer queue previously created by UfxEndpointCreate. |
| [UfxEndpointInitSetEventCallbacks function](nf-ufxclient-ufxendpointinitseteventcallbacks.md) | Initialize a UFXENDPOINT_INIT structure. |
| [UfxEndpointNotifySetup function](nf-ufxclient-ufxendpointnotifysetup.md) | Notifies UFX when the client driver receives a setup packet from the host. |
| [UfxFdoInit function](nf-ufxclient-ufxfdoinit.md) | Initializes the WDFDEVICE_INIT structure that the client driver subsequently provides when it calls WdfDeviceCreate. |

## Callback functions

| Title   | Description   |
| ---- |:---- |
| [EVT_UFX_DEVICE_ADDRESSED callback](nc-ufxclient-evt_ufx_device_addressed.md) | The client driver's implementation to assign an address on the function controller. |
| [EVT_UFX_DEVICE_CONTROLLER_RESET callback](nc-ufxclient-evt_ufx_device_controller_reset.md) | The client driver's implementation to reset the function controller to its initial state. |
| [EVT_UFX_DEVICE_DEFAULT_ENDPOINT_ADD callback](nc-ufxclient-evt_ufx_device_default_endpoint_add.md) | The client driver's implementation to create a default control endpoint. |
| [EVT_UFX_DEVICE_ENDPOINT_ADD callback](nc-ufxclient-evt_ufx_device_endpoint_add.md) | The client driver's implementation to create a default endpoint object. |
| [EVT_UFX_DEVICE_HOST_CONNECT callback](nc-ufxclient-evt_ufx_device_host_connect.md) | The client driver's implementation to initiate connection with the host. |
| [EVT_UFX_DEVICE_HOST_DISCONNECT callback](nc-ufxclient-evt_ufx_device_host_disconnect.md) | The client driver's implementation to disable the function controller's communication with the host. |
| [EVT_UFX_DEVICE_PORT_CHANGE callback](nc-ufxclient-evt_ufx_device_port_change.md) | The client driver's implementation to update the type of the new port to which the USB device is connected. |
| [EVT_UFX_DEVICE_PORT_DETECT callback](nc-ufxclient-evt_ufx_device_port_detect.md) | The client driver's implementation to initiate port detection. |
| [EVT_UFX_DEVICE_PROPRIETARY_CHARGER_DETECT callback](nc-ufxclient-evt_ufx_device_proprietary_charger_detect.md) | The client driver's implementation to initiate proprietary charger detection. |
| [EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET callback](nc-ufxclient-evt_ufx_device_proprietary_charger_reset.md) | The client driver's implementation to resets proprietary charger. |
| [EVT_UFX_DEVICE_PROPRIETARY_CHARGER_SET_PROPERTY callback](nc-ufxclient-evt_ufx_device_proprietary_charger_set_property.md) | The client driver's implementation to set charger information that it uses to enable charging over USB. |
| [EVT_UFX_DEVICE_REMOTE_WAKEUP_SIGNAL callback](nc-ufxclient-evt_ufx_device_remote_wakeup_signal.md) | The client driver's implementation to initiate remote wake-up on the function controller. |
| [EVT_UFX_DEVICE_SUPER_SPEED_POWER_FEATURE callback](nc-ufxclient-evt_ufx_device_super_speed_power_feature.md) | The client driver's implementation to set or clear the specified power feature on the function controller. |
| [EVT_UFX_DEVICE_TESTHOOK callback](nc-ufxclient-evt_ufx_device_testhook.md) | This IOCTL code is not supported. |
| [EVT_UFX_DEVICE_TEST_MODE_SET callback](nc-ufxclient-evt_ufx_device_test_mode_set.md) | The client driver's implementation to set the test mode of the function controller. |
| [EVT_UFX_DEVICE_USB_STATE_CHANGE callback](nc-ufxclient-evt_ufx_device_usb_state_change.md) | The client driver's implementation to update the state of the USB device. |

## Structures

| Title   | Description   |
| ---- |:---- |
| [_UFX_DEVICE_CALLBACKS structure](ns-ufxclient-_ufx_device_callbacks.md) | The UFX_DEVICE_CALLBACKS structure is used to define then event callback functions supported by the client driver. |
| [_UFX_ENDPOINT_CALLBACKS structure](ns-ufxclient-_ufx_endpoint_callbacks.md) | The UFX_ENDPOINT_CALLBACKS structure is used to define then event callback functions supported by the client driver. |
