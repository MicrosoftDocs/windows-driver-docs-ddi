---
UID: NF:ucmtcpciportcontroller.UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION_INIT
title: UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION_INIT function (ucmtcpciportcontroller.h)
description: Initializes the UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION structure.
old-location: buses\ucmtcpci_port_controller_identification_init.htm
tech.root: usbref
ms.assetid: 4204b849-8195-4a1b-9bb3-1e9cbeb12223
ms.date: 05/07/2018
keywords: ["UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION_INIT function"]
ms.keywords: UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION_INIT, UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION_INIT method [Buses], buses.ucmtcpci_port_controller_identification_init, ucmtcpciportcontroller/UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION_INIT
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
targetos: Windows
req.typenames: 
f1_keywords:
 - UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION_INIT
 - ucmtcpciportcontroller/UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION_INIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ucmtcpciportcontroller.h
api_name:
 - UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION_INIT
---

# UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION_INIT function


## -description

                        Initializes the <a href="/windows-hardware/drivers/ddi/ucmtcpciportcontroller/ns-ucmtcpciportcontroller-_ucmtcpci_port_controller_identification">UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION</a> structure.

## -parameters

### -param Identification 

[out]
A pointer to the driver-allocated <b>UCMTCPCI_PORT_CONTROLLER_IDENTIFICATION</b> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ucmtcpciportcontroller/nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate">UcmTcpciPortControllerCreate</a>