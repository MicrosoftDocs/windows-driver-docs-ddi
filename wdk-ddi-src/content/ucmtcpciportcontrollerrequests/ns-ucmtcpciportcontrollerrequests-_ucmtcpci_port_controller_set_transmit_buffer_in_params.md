---
UID: NS:ucmtcpciportcontrollerrequests._UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS
title: _UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS (ucmtcpciportcontrollerrequests.h)
description: Stores the value of the TRANSMIT_BUFFER Register. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER request.
old-location: buses\ucmtcpci_port_controller_set_transmit_buffer_in_params.htm
tech.root: usbref
ms.assetid: bcce81ce-7075-41a6-a8ab-95fe0f83436c
ms.date: 05/07/2018
ms.keywords: "*PUCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS, PUCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS, PUCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS structure pointer [Buses], UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS, UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS structure [Buses], _UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS, buses.ucmtcpci_port_controller_set_transmit_buffer_in_params, ucmtcpciportcontrollerrequests/PUCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS, ucmtcpciportcontrollerrequests/UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS"
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ucmtcpciportcontrollerrequests.h
api_name:
-	UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS
product:
- Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS
---

# _UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER_IN_PARAMS structure


## -description



             Stores the value of the TRANSMIT_BUFFER Register. This structure is used in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt805840">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER</a> request.
                 


## -struct-fields




### -field PortControllerObject

Handle to the port controller object that the client driver received in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt805844">UcmTcpciPortControllerCreate</a>.


### -field TransmitBuffer

A pointer to the 
                     <b>UCMTCPCI_PORT_CONTROLLER_TRANSMIT_BUFFER</b> structure that contains 
                 the value to set in the TRANSMIT_BUFFER  Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. This structure is declared in UcmTcpciSpec.h.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt805840">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_TRANSMIT_BUFFER</a>
 

 

