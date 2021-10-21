---
UID: NS:ucmtcpciportcontrollerrequests._UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS
title: _UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS (ucmtcpciportcontrollerrequests.h)
description: Stores the values of TRANSMIT Register. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT request.
old-location: buses\ucmtcpci_port_controller_set_transmit_in_params.htm
tech.root: usbref
ms.date: 09/14/2021
keywords: ["UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS structure"]
ms.keywords: "*PUCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS, PUCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS, PUCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS structure pointer [Buses], UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS, UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS structure [Buses], _UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS, buses.ucmtcpci_port_controller_set_transmit_in_params, ucmtcpciportcontrollerrequests/PUCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS, ucmtcpciportcontrollerrequests/UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS"
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
req.typenames: UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS
f1_keywords:
 - _UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS
 - ucmtcpciportcontrollerrequests/_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS
 - PUCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS
 - ucmtcpciportcontrollerrequests/PUCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS
 - UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS
 - ucmtcpciportcontrollerrequests/UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ucmtcpciportcontrollerrequests.h
api_name:
 - _UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS
 - PUCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS
 - UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS
---

# _UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_IN_PARAMS structure

## -description

Stores the values of TRANSMIT Register. This structure is used in the [IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT](./ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_transmit.md) request.

## -struct-fields

### -field PortControllerObject

Handle to the port controller object that the client driver received in the previous call to [UcmTcpciPortControllerCreate](../ucmtcpciportcontroller/nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate.md).

### -field Transmit

A pointer to the **UCMTCPCI_PORT_CONTROLLER_TRANSMIT** structure that contains the value to set in the TRANSMIT register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. This structure is declared in UcmTcpciSpec.h.

## -see-also

[IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT](./ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_transmit.md)