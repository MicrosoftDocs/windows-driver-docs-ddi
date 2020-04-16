---
UID: NF:ucmtcpciportcontroller.UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT
title: UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT function (ucmtcpciportcontroller.h)
description: Initializes the UCMTCPCI_PORT_CONTROLLER_CONFIG structure.
old-location: buses\ucmtcpci_port_controller_config_init.htm
tech.root: usbref
ms.assetid: 8e9718e1-2f7c-4322-a34d-2faa45f4f97e
ms.date: 05/07/2018
keywords: ["UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT function"]
ms.keywords: UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT, UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT method [Buses], buses.ucmtcpci_port_controller_config_init, ucmtcpciportcontroller/UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT
f1_keywords:
 - "ucmtcpciportcontroller/UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT"
req.header: ucmtcpciportcontroller.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ucmtcpciportcontroller.h
api_name:
- UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# UCMTCPCI_PORT_CONTROLLER_CONFIG_INIT function


## -description



                        Initializes the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontroller/ns-ucmtcpciportcontroller-_ucmtcpci_port_controller_config">UCMTCPCI_PORT_CONTROLLER_CONFIG</a> structure.
                


## -parameters




### -param Config [out]

A pointer to the driver-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontroller/ns-ucmtcpciportcontroller-_ucmtcpci_port_controller_config">UCMTCPCI_PORT_CONTROLLER_CONFIG</a> structure.


### -param Identification [in]

A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontroller/ns-ucmtcpciportcontroller-_ucmtcpci_port_controller_identification">UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION</a> structure.


### -param Capabilities [in]

 A pointer to the 
                 <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontroller/ns-ucmtcpciportcontroller-_ucmtcpci_port_controller_capabilities">UCMTCPCI_PORT_CONTROLLER_CAPABILITIES</a> structure.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontroller/nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate">UcmTcpciPortControllerCreate</a>
 

 

