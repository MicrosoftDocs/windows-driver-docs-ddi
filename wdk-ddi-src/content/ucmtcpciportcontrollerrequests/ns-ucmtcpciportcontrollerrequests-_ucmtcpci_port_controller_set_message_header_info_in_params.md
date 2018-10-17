---
UID: NS:ucmtcpciportcontrollerrequests._UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO_IN_PARAMS
title: "_UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO_IN_PARAMS"
author: windows-driver-content
description: Stores the value of the VBUS_VOLTAGE_ALARM_LO_CFG Register. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO request.
old-location: buses\ucmtcpci_port_controller_set_message_header_info_in_params.htm
tech.root: usbref
ms.assetid: 1efccde1-1e96-4a38-aa5a-5b386ad10e51
ms.date: 5/7/2018
ms.keywords: "*PUCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO_IN_PARAMS, PUCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO_IN_PARAMS, PUCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO_IN_PARAMS structure pointer [Buses], UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO_IN_PARAMS, UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO_IN_PARAMS structure [Buses], _UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO_IN_PARAMS, buses.ucmtcpci_port_controller_set_message_header_info_in_params, ucmtcpciportcontrollerrequests/PUCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO_IN_PARAMS, ucmtcpciportcontrollerrequests/UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO_IN_PARAMS"
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
-	UcmTcpciPortControllerRequests.h
api_name:
-	UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO_IN_PARAMS
product:
- Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO_IN_PARAMS
---

# _UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO_IN_PARAMS structure


## -description



             Stores the value of the VBUS_VOLTAGE_ALARM_LO_CFG Register. This structure is used in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt805837">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO</a> request.
                 


## -struct-fields




### -field PortControllerObject

Handle to the port controller object that the client driver received in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt805844">UcmTcpciPortControllerCreate</a>.


### -field MessageHeaderInfo


                     A 
                 <b>UCMTCPCI_PORT_CONTROLLER_MESSAGE_HEADER_INFO</b> structure that describes the MESSAGE_HEADER_INFO Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. This structure is declared in UcmTcpciSpec.h.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt805837">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_MESSAGE_HEADER_INFO</a>
 

 

