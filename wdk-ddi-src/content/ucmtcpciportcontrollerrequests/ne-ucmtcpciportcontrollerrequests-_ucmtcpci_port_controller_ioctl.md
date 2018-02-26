---
UID: NE:ucmtcpciportcontrollerrequests._UCMTCPCI_PORT_CONTROLLER_IOCTL
title: "_UCMTCPCI_PORT_CONTROLLER_IOCTL"
author: windows-driver-content
description: Defines the various device I/O control requests that are sent to the client driver for the port controller. This indicates the type of IOCTL in WPP.
old-location: buses\ucmtcpci_port_controller_ioctl.htm
old-project: usbref
ms.assetid: 61dcd4d9-cfd9-4878-96f5-c95465e0949e
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, C, E, I, L, M, N, O, P, R, T, U, UCMTCPCI_PORT_CONTROLLER_IOCTL, UCMTCPCI_PORT_CONTROLLER_IOCTL enumeration [Buses], _, _IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED, _IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED, _IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED, _IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED, _IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL, _IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS, _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND, _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT, _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL, _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO, _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT, _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT, _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER, _UCMTCPCI_PORT_CONTROLLER_IOCTL, buses.ucmtcpci_port_controller_ioctl, ucmtcpciportcontrollerrequests/UCMTCPCI_PORT_CONTROLLER_IOCTL, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT, ucmtcpciportcontrollerrequests/_IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	UcmTcpciPortControllerRequests.h
apiname:
-	UCMTCPCI_PORT_CONTROLLER_IOCTL
product: Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_IOCTL
req.product: Windows 10 or later.
---

# _UCMTCPCI_PORT_CONTROLLER_IOCTL enumeration


## -description


Defines the various device I/O control requests that are sent to the client driver for the port controller. This indicates the type of IOCTL in WPP.
                


## -syntax


````
typedef enum _UCMTCPCI_PORT_CONTROLLER_IOCTL { 
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS                      = = IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL                     = = IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL                     = = IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT                    = = IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER             = = IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT              = = IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT      = = IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND                     = = IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO         = = IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED          = IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED           = IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED          = IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED,
  _IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED  = IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED
} UCMTCPCI_PORT_CONTROLLER_IOCTL;
````


## -enum-fields




### -field _IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS


                        
                    The <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_get_status.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS</a> request.


### -field _IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL


                        
                    The <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_get_control.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL</a> request.


### -field _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL


                        
                    The <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_control.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONTROL</a> request.


### -field _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT


                        
                    The <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_transmit.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT</a> request.


### -field _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER


                        
                    The  <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_transmit_buffer.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER</a> request.


### -field _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT


                        
                    The <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_receive_detect.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT</a> request.


### -field _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT


                        
                    The <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_config_standard_output.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_CONFIG_STANDARD_OUTPUT</a> request.


### -field _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND


                        
                    The <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_command.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND</a> request.


### -field _IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO


                        
                    The <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_message_header_info.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO</a> request.


### -field _IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED

The <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_alternate_mode_entered.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_ENTERED</a> request.


### -field _IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED

The <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_alternate_mode_exited.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_ALTERNATE_MODE_EXITED</a> request.


### -field _IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED

The <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_displayport_configured.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED</a> request.


### -field _IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED

The  <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_displayport_hpd_status_changed.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED</a> request.


### -field _IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_DISPLAY_OUT_STATUS_CHANGED



