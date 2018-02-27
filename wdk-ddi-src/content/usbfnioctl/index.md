---
UID: NA:usbfnioctl
ms.assetid: 346c06db-ae00-3b42-a05a-d786904c5f0f
ms.author: windowsdriverdev
ms.date: 02/26/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Usbfnioctl.h header



This header is used by Universal Serial Bus(USB). For more information, see
- [Universal Serial Bus(USB)](../_usbref/index.md)

Usbfnioctl.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_USBFN_POWER_FILTER_STATE structure](ns-usbfnioctl-_usbfn_power_filter_state.md) | Reserved. Do not use. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_INTERNAL_USBFN_ACTIVATE_USB_BUS IOCTL](ni-usbfnioctl-ioctl_internal_usbfn_activate_usb_bus.md) | The USB class driver sends this request to activate the bus so that the driver can prepare to process bus events and handle traffic. |
| [IOCTL_INTERNAL_USBFN_BUS_EVENT_NOTIFICATION IOCTL](ni-usbfnioctl-ioctl_internal_usbfn_bus_event_notification.md) | The USB class driver sends this request to prepare for notifications received from the USB function class extension (UFX) in response to an event on the bus, such as a change in the port type or a receipt of a non-standard setup packet. |
| [IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_IN IOCTL](ni-usbfnioctl-ioctl_internal_usbfn_control_status_handshake_in.md) | The class driver sends this request to send a zero-length control status handshake on endpoint 0 in the IN direction. |
| [IOCTL_INTERNAL_USBFN_CONTROL_STATUS_HANDSHAKE_OUT IOCTL](ni-usbfnioctl-ioctl_internal_usbfn_control_status_handshake_out.md) | The class driver sends this request to send a zero-length control status handshake on endpoint 0 in the OUT direction. |
| [IOCTL_INTERNAL_USBFN_DEACTIVATE_USB_BUS IOCTL](ni-usbfnioctl-ioctl_internal_usbfn_deactivate_usb_bus.md) | Do not use. |
| [IOCTL_INTERNAL_USBFN_GET_CLASS_INFO IOCTL](ni-usbfnioctl-ioctl_internal_usbfn_get_class_info.md) | The class driver sends this request IO control code to retrieve information about the available pipes for a device, as configured in the registry. |
| [IOCTL_INTERNAL_USBFN_GET_INTERFACE_DESCRIPTOR_SET IOCTL](ni-usbfnioctl-ioctl_internal_usbfn_get_interface_descriptor_set.md) | The class driver sends this request to get the entire USB interface descriptor set for a function on the device. |
| [IOCTL_INTERNAL_USBFN_GET_PIPE_STATE IOCTL](ni-usbfnioctl-ioctl_internal_usbfn_get_pipe_state.md) | The class driver sends this request to get the stall state of the specified pipe. |
| [IOCTL_INTERNAL_USBFN_REGISTER_USB_STRING IOCTL](ni-usbfnioctl-ioctl_internal_usbfn_register_usb_string.md) | The class driver sends this request to register a USB string descriptor. |
| [IOCTL_INTERNAL_USBFN_RESERVED IOCTL](ni-usbfnioctl-ioctl_internal_usbfn_reserved.md) | Do not use. |
| [IOCTL_INTERNAL_USBFN_SET_PIPE_STATE IOCTL](ni-usbfnioctl-ioctl_internal_usbfn_set_pipe_state.md) | The class driver sends this request to set the stall state of the specified USB pipe. |
| [IOCTL_INTERNAL_USBFN_SET_POWER_FILTER_EXIT_LPM IOCTL](ni-usbfnioctl-ioctl_internal_usbfn_set_power_filter_exit_lpm.md) | Do not use. |
| [IOCTL_INTERNAL_USBFN_SET_POWER_FILTER_STATE IOCTL](ni-usbfnioctl-ioctl_internal_usbfn_set_power_filter_state.md) | Do not use. |
| [IOCTL_INTERNAL_USBFN_SIGNAL_REMOTE_WAKEUP IOCTL](ni-usbfnioctl-ioctl_internal_usbfn_signal_remote_wakeup.md) | The class driver sends this request to get remote wake-up notifications from endpoints. |
| [IOCTL_INTERNAL_USBFN_TRANSFER_IN IOCTL](ni-usbfnioctl-ioctl_internal_usbfn_transfer_in.md) | The class driver sends this request to initiate a data transfer to the host on the specified pipe. |
| [IOCTL_INTERNAL_USBFN_TRANSFER_IN_APPEND_ZERO_PKT IOCTL](ni-usbfnioctl-ioctl_internal_usbfn_transfer_in_append_zero_pkt.md) | The class driver sends this request to initiate an IN transfer to the specified pipe and appends a zero-length packet to indicate the end of the transfer. |
| [IOCTL_INTERNAL_USBFN_TRANSFER_OUT IOCTL](ni-usbfnioctl-ioctl_internal_usbfn_transfer_out.md) | The class driver sends this request to initiate a data transfer from the host on the specified pipe. |
