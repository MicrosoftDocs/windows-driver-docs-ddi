---
UID: NS:ucmtcpciportcontroller._UCMTCPCI_PORT_CONTROLLER_CONFIG
title: _UCMTCPCI_PORT_CONTROLLER_CONFIG (ucmtcpciportcontroller.h)
description: Contains configuration options for the port controller object, passed by the client driver in the call to UcmTcpciPortControllerCreate. Call UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT to initialize this structure.
old-location: buses\ucmtcpci_port_controller_config.htm
tech.root: usbref
ms.assetid: a9027cda-0851-46e2-9006-0d757109fc3a
ms.date: 05/07/2018
keywords: ["_UCMTCPCI_PORT_CONTROLLER_CONFIG structure"]
ms.keywords: "*PUCMTCPCI_PORT_CONTROLLER_CONFIG, PUCMTCPCI_PORT_CONTROLLER_CONFIG, PUCMTCPCI_PORT_CONTROLLER_CONFIG structure pointer [Buses], UCMTCPCI_PORT_CONTROLLER_CONFIG, UCMTCPCI_PORT_CONTROLLER_CONFIG structure [Buses], _UCMTCPCI_PORT_CONTROLLER_CONFIG, buses.ucmtcpci_port_controller_config, ucmtcpciportcontroller/PUCMTCPCI_PORT_CONTROLLER_CONFIG, ucmtcpciportcontroller/UCMTCPCI_PORT_CONTROLLER_CONFIG"
f1_keywords:
 - "ucmtcpciportcontroller/UCMTCPCI_PORT_CONTROLLER_CONFIG"
req.header: ucmtcpciportcontroller.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ucmtcpciportcontroller.h
api_name:
- UCMTCPCI_PORT_CONTROLLER_CONFIG
product:
- Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_CONFIG, *PUCMTCPCI_PORT_CONTROLLER_CONFIG
---

# _UCMTCPCI_PORT_CONTROLLER_CONFIG structure


## -description



                 Contains configuration options for the port controller object,  passed by the client driver in the call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontroller/nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate">UcmTcpciPortControllerCreate</a>. Call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontroller/nf-ucmtcpciportcontroller-ucmtcpci_port_controller_config_init">UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT</a> to initialize this structure.
             


## -struct-fields




### -field Size


                     Size of this structure.
                 


### -field Identification

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontroller/ns-ucmtcpciportcontroller-_ucmtcpci_port_controller_identification">UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION</a> structure.


### -field Capabilities

 A pointer to the 
                 <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontroller/ns-ucmtcpciportcontroller-_ucmtcpci_port_controller_capabilities">UCMTCPCI_PORT_CONTROLLER_CAPABILITIES</a> structure.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontroller/nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate">UcmTcpciPortControllerCreate</a>
 

 

