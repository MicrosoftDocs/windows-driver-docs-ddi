---
UID: NS:ucmtcpciportcontrollerrequests._UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS
title: "_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS"
description: Stores the values of all control registers of the port controller retrieved by the IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL request.
old-location: buses\ucmtcpci_port_controller_get_control_out_params.htm
tech.root: usbref
ms.assetid: c75167cb-14c9-4189-961a-97a50c84d6be
ms.date: 05/07/2018
ms.keywords: "*PUCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS, PUCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS, PUCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS structure pointer [Buses], UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS, UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS structure [Buses], _UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS, buses.ucmtcpci_port_controller_get_control_out_params, ucmtcpciportcontrollerrequests/PUCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS, ucmtcpciportcontrollerrequests/UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS"
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
-	UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS
product:
- Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS
---

# _UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_OUT_PARAMS structure


## -description



             Stores the values of all control registers of the port controller retrieved by the 
             <a href="https://msdn.microsoft.com/library/windows/hardware/mt805832">IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL</a> request.


## -struct-fields




### -field TCPCControl


                     A 
                 <b>UCMTCPCI_PORT_CONTROLLER_TCPC_CONTROL</b> structure that describes the TCPC_CONTROL Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. This structure is declared in UcmTcpciSpec.h.


### -field RoleControl


                     A 
                 <b>UCMTCPCI_PORT_CONTROLLER_ROLE_CONTROL</b> structure that describes the ROLE_CONTROL Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. This structure is declared in UcmTcpciSpec.h.


### -field FaultControl


                     A 
                 <b>UCMTCPCI_PORT_CONTROLLER_FAULT_CONTROL</b> structure that describes the FAULT_CONTROL Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. This structure is declared in UcmTcpciSpec.h.


### -field PowerControl


                     A 
                 <b>UCMTCPCI_PORT_CONTROLLER_POWER_CONTROL</b> structure that describes the FAULT_POWER Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. This structure is declared in UcmTcpciSpec.h.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt805832">IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL</a>
 

 

