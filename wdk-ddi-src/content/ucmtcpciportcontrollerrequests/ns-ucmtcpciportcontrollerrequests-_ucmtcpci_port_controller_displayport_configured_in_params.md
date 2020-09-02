---
UID: NS:ucmtcpciportcontrollerrequests._UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS
title: _UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS (ucmtcpciportcontrollerrequests.h)
description: Stores information about the pin assignment of the DisplayPort alternate mode that was configured. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED request.
old-location: buses\ucmtcpci_port_controller_displayport_configured_in_params.htm
tech.root: usbref
ms.assetid: 91672EF6-3795-4DE1-9C7B-76E68490D0E6
ms.date: 05/07/2018
keywords: ["UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS structure"]
ms.keywords: "*PUCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS, PUCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS, PUCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS structure pointer [Buses], UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS, UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS structure [Buses], _UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS, buses.ucmtcpci_port_controller_displayport_configured_in_params, ucmtcpciportcontrollerrequests/PUCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS, ucmtcpciportcontrollerrequests/UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS"
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
req.typenames: UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS
f1_keywords:
 - _UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS
 - ucmtcpciportcontrollerrequests/_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS
 - PUCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS
 - ucmtcpciportcontrollerrequests/PUCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS
 - UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS
 - ucmtcpciportcontrollerrequests/UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ucmtcpciportcontrollerrequests.h
api_name:
 - UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS
---

# _UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED_IN_PARAMS structure


## -description

Stores information about the  pin assignment of the DisplayPort alternate mode that was configured. This structure is used in the 
             <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_displayport_configured">IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED</a>  request.

## -struct-fields

### -field PortControllerObject

Handle to the port controller object that the client driver received in the previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontroller/nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate">UcmTcpciPortControllerCreate</a>.

### -field PinAssignment

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ne-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_displayport_pin_assignment">UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_PIN_ASSIGNMENT</a>-type value that indicates the pin that was configured.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontrollerrequests/ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_displayport_configured">IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_CONFIGURED</a>

