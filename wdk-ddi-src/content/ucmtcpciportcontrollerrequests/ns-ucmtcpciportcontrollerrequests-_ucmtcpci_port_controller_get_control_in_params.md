---
UID: NS:ucmtcpciportcontrollerrequests._UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS
title: _UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS (ucmtcpciportcontrollerrequests.h)
description: This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL request.
old-location: buses\ucmtcpci_port_controller_get_control_in_params.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS structure"]
ms.keywords: "*PUCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS, PUCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS, PUCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS structure pointer [Buses], UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS, UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS structure [Buses], _UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS, buses.ucmtcpci_port_controller_get_control_in_params, ucmtcpciportcontrollerrequests/PUCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS, ucmtcpciportcontrollerrequests/UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS"
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
req.typenames: UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS
f1_keywords:
 - _UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS
 - ucmtcpciportcontrollerrequests/_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS
 - PUCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS
 - ucmtcpciportcontrollerrequests/PUCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS
 - UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS
 - ucmtcpciportcontrollerrequests/UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ucmtcpciportcontrollerrequests.h
api_name:
 - UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS
---

# _UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS structure


## -description

             This structure is used in the 
             <a href="/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_get_control">IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL</a>  request.

## -struct-fields

### -field PortControllerObject

Handle to the port controller object that the client driver received in the previous call to <a href="/windows-hardware/drivers/ddi/ucmtcpciportcontroller/nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate">UcmTcpciPortControllerCreate</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_get_control">IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL</a>
