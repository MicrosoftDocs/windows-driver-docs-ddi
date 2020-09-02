---
UID: NE:ucmtcpciportcontrollerrequests._UCMTCPCI_PORT_CONTROLLER_IOCTL
title: _UCMTCPCI_PORT_CONTROLLER_IOCTL (ucmtcpciportcontrollerrequests.h)
description: Defines the various device I/O control requests that are sent to the client driver for the port controller. This indicates the type of IOCTL in WPP.
old-location: buses\ucmtcpci_port_controller_ioctl.htm
tech.root: usbref
ms.assetid: 61dcd4d9-cfd9-4878-96f5-c95465e0949e
ms.date: 05/07/2018
keywords: ["UCMTCPCI_PORT_CONTROLLER_IOCTL enumeration"]
ms.keywords: UCMTCPCI_PORT_CONTROLLER_IOCTL, UCMTCPCI_PORT_CONTROLLER_IOCTL enumeration [Buses], _IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED, _IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED, _IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED, _IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED, _IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL, _IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS, _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND, _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT, _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL, _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO, _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT, _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT, _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER, _UCMTCPCI_PORT_CONTROLLER_IOCTL, buses.ucmtcpci_port_controller_ioctl, ucmtcpciportcontrollerrequests/UCMTCPCI_PORT_CONTROLLER_IOCTL, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER
req.header: ucmtcpciportcontrollerrequests.h
req.include-header: 
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
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_IOCTL
f1_keywords:
 - _UCMTCPCI_PORT_CONTROLLER_IOCTL
 - ucmtcpciportcontrollerrequests/_UCMTCPCI_PORT_CONTROLLER_IOCTL
 - UCMTCPCI_PORT_CONTROLLER_IOCTL
 - ucmtcpciportcontrollerrequests/UCMTCPCI_PORT_CONTROLLER_IOCTL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - UcmTcpciPortControllerRequests.h
api_name:
 - UCMTCPCI_PORT_CONTROLLER_IOCTL
---

# _UCMTCPCI_PORT_CONTROLLER_IOCTL enumeration


## -description

Defines the various device I/O control requests that are sent to the client driver for the port controller. This indicates the type of IOCTL in WPP.

## -enum-fields

### -field _IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS

                        
                    The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_get_status">IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS</a> request.

### -field _IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL

                        
                    The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_get_control">IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL</a> request.

### -field _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL

                        
                    The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_control">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL</a> request.

### -field _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT

                        
                    The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_transmit">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT</a> request.

### -field _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER

                        
                    The  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_transmit_buffer">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER</a> request.

### -field _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT

                        
                    The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_receive_detect">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT</a> request.

### -field _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT

                        
                    The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_config_standard_output">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT</a> request.

### -field _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND

                        
                    The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_command">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND</a> request.

### -field _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO

                        
                    The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_message_header_info">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO</a> request.

### -field _IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_alternate_mode_entered">IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED</a> request.

### -field _IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_alternate_mode_exited">IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED</a> request.

### -field _IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED

The <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_displayport_configured">IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED</a> request.

### -field _IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED

The  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_displayport_hpd_status_changed">IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED</a> request.

### -field _IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_DISPLAY_OUT_STATUS_CHANGED

