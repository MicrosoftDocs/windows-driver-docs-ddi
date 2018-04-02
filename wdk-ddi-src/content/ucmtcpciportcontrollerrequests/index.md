---
UID: NA:ucmtcpciportcontrollerrequests
ms.assetid: 890a830c-7cf8-330c-8a38-9d2db62fcaf4
ms.author: windowsdriverdev
ms.date: 02/27/18
ms.keywords: 
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: portal
---

# Ucmtcpciportcontrollerrequests.h header



This header is used by Universal Serial Bus(USB). For more information, see
- [Universal Serial Bus(USB)](../_usbref/index.md)

Ucmtcpciportcontrollerrequests.h contain these programming interfaces:


## Structures

| Title   | Description   |
| ---- |:---- |
| [_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED_IN_PARAMS structure](ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_alternate_mode_entered_in_params.md) | Stores information about the alternate mode that was detected. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED request. |
| [_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED_IN_PARAMS structure](ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_alternate_mode_exited_in_params.md) | Stores information about the alternate mode that was exited. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED request. |
| [_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS structure](ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_displayport_configured_in_params.md) | Stores information about the pin assignment of the DisplayPort alternate mode that was configured. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED request. |
| [_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_DISPLAY_OUT_STATUS_CHANGED_IN_PARAMS structure](ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_displayport_display_out_status_changed_in_params.md) | Stores information about display out status of the DisplayPort connection. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_DISPLAY_OUT_STATUS_CHANGED request. |
| [_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED_IN_PARAMS structure](ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_displayport_hpd_status_changed_in_params.md) | Stores information about hot plug detect status of the DisplayPort connection. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED request. |
| [_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS structure](ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_get_control_in_params.md) | This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL request. |
| [_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS structure](ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_get_control_out_params.md) | Stores the values of all control registers of the port controller retrieved by the IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL request. |
| [_UCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS structure](ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_get_status_in_params.md) | This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS request. |
| [_UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS structure](ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_get_status_out_params.md) | Stores the values of all status registers of the port controller. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS request. |
| [_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND_IN_PARAMS structure](ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_set_command_in_params.md) | Stores the specified command registers. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND request. |
| [_UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT_IN_PARAMS structure](ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_set_config_standard_output_in_params.md) | Stores the value of the CONFIG_STANDARD_OUTPUT Register. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT request. |
| [_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL_IN_PARAMS structure](ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_set_control_in_params.md) | Stores the values of all control registers. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL request. |
| [_UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO_IN_PARAMS structure](ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_set_message_header_info_in_params.md) | Stores the value of the VBUS_VOLTAGE_ALARM_LO_CFG Register. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO request. |
| [_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT_IN_PARAMS structure](ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_set_receive_detect_in_params.md) | Stores the value of the RECEIVE_DETECT Register. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT request. |
| [_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS structure](ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_set_transmit_buffer_in_params.md) | Stores the value of the TRANSMIT_BUFFER Register. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER request. |
| [_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS structure](ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_set_transmit_in_params.md) | Stores the values of TRANSMIT Register. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT request. |

## I/O control codes

| Title   | Description   |
| ---- |:---- |
| [IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED IOCTL](ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_alternate_mode_entered.md) | Notifies the client driver that an alternate mode is entered so that the driver can perform additional tasks. |
| [IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED IOCTL](ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_alternate_mode_exited.md) | Notifies the client driver that an alternate mode is exited so that the driver can perform additional tasks. |
| [IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED IOCTL](ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_displayport_configured.md) | Notifies the client driver that the DisplayPort alternate mode on the partner device has been configured with pin assignment so that the driver can perform additional tasks. |
| [IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_DISPLAY_OUT_STATUS_CHANGED IOCTL](ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_displayport_display_out_status_changed.md) | Notifies the client driver that the display out status of the DisplayPort connection has changed so that the driver can perform additional tasks. |
| [IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED IOCTL](ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_displayport_hpd_status_changed.md) | Notifies the client driver that the hot-plug detect status of the DisplayPort connection has changed so that the driver can perform additional tasks. |
| [IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL IOCTL](ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_get_control.md) | Gets the values of all control registers defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. |
| [IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS IOCTL](ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_get_status.md) | Gets values of all status registers as per the Universal Serial Bus Type-C Port Controller Interface Specification. The client driver must retrieve the values of the CC_STATUS, POWER_STATUS, and FAULT_STATUS registers. |
| [IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND IOCTL](ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_command.md) | Sets the value of a command register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. |
| [IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT IOCTL](ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_config_standard_output.md) | Sets the CONFIG_STANDARD_OUTPUT Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. |
| [IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL IOCTL](ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_control.md) | Sets the value of a control register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. |
| [IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO IOCTL](ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_message_header_info.md) | Sets the value of the MESSAGE_HEADER_INFO Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. |
| [IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT IOCTL](ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_receive_detect.md) | Sets the RECEIVE_DETECT Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. |
| [IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT IOCTL](ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_transmit.md) | Sets the TRANSMIT Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. |
| [IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER IOCTL](ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_transmit_buffer.md) | Sets the TRANSMIT_BUFER Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. |

## Enumerations

| Title   | Description   |
| ---- |:---- |
| [_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_DISPLAY_OUT_STATUS enumeration](ne-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_displayport_display_out_status.md) | Defines values to determine whether a display out status for a DisplayPort device is enabled. |
| [_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS enumeration](ne-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_displayport_hpd_status.md) | Defines values to determine whether a DisplayPort device is plugged in. |
| [_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_PIN_ASSIGNMENT enumeration](ne-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_displayport_pin_assignment.md) | TBD. |
| [_UCMTCPCI_PORT_CONTROLLER_IOCTL enumeration](ne-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_ioctl.md) | Defines the various device I/O control requests that are sent to the client driver for the port controller. This indicates the type of IOCTL in WPP. |
