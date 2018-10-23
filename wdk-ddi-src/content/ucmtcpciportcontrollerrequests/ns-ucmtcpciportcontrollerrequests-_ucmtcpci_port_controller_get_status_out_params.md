---
UID: NS:ucmtcpciportcontrollerrequests._UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS
title: "_UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS"
author: windows-driver-content
description: Stores the values of all status registers of the port controller. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS request.
old-location: buses\ucmtcpci_port_controller_get_status_out_params.htm
tech.root: usbref
ms.assetid: e43b2a10-20b5-4cb8-ae7b-fc1feb7a4bf1
ms.date: 05/07/2018
ms.keywords: "*PUCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS, PUCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS, PUCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS structure pointer [Buses], UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS, UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS structure [Buses], _UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS, buses.ucmtcpci_port_controller_get_status_out_params, ucmtcpciportcontrollerrequests/PUCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS, ucmtcpciportcontrollerrequests/UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS"
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
-	UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS
product:
- Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS
---

# _UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS structure


## -description



             Stores the values of all status registers of the port controller. This structure is used in the 
             <a href="https://msdn.microsoft.com/library/windows/hardware/mt805833">IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS</a> request.


## -struct-fields




### -field CCStatus


                     A 
                 <b>UCMTCPCI_PORT_CONTROLLER_CC_STATUS</b> structure that describes the CC_STATUS Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. This structure is declared in UcmTcpciSpec.h.


### -field PowerStatus


                     A 
                 <b>UCMTCPCI_PORT_CONTROLLER_POWER_STATUS</b> structure that describes the POWER_STATUS Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. This structure is declared in UcmTcpciSpec.h.


### -field FaultStatus


                     A 
                 <b>UCMTCPCI_PORT_CONTROLLER_FAULT_STATUS</b> structure that describes the FAULT_STATUS Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. This structure is declared in UcmTcpciSpec.h.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt805833">IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS</a>
 

 

