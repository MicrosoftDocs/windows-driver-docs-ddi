---
UID: NF:ucmtcpciportcontroller.UCMTCPCI_PORT_CONTROLLER_ALERT_DATA_INIT
title: UCMTCPCI_PORT_CONTROLLER_ALERT_DATA_INIT function (ucmtcpciportcontroller.h)
description: Initializes the UCMTCPCI_PORT_CONTROLLER_ALERT_DATA structure.
old-location: buses\ucmtcpci_port_controller_alert_data_init.htm
tech.root: usbref
ms.assetid: 7c3276cc-9194-4c18-b1d8-2795efbeb357
ms.date: 05/07/2018
keywords: ["UCMTCPCI_PORT_CONTROLLER_ALERT_DATA_INIT function"]
ms.keywords: UCMTCPCI_PORT_CONTROLLER_ALERT_DATA_INIT, UCMTCPCI_PORT_CONTROLLER_ALERT_DATA_INIT method [Buses], buses.ucmtcpci_port_controller_alert_data_init, ucmtcpciportcontroller/UCMTCPCI_PORT_CONTROLLER_ALERT_DATA_INIT
f1_keywords:
 - "ucmtcpciportcontroller/UCMTCPCI_PORT_CONTROLLER_ALERT_DATA_INIT"
 - "UCMTCPCI_PORT_CONTROLLER_ALERT_DATA_INIT"
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
- UCMTCPCI_PORT_CONTROLLER_ALERT_DATA_INIT
product:
- Windows
targetos: Windows
req.typenames: 
---

# UCMTCPCI_PORT_CONTROLLER_ALERT_DATA_INIT function


## -description



                        Initializes the <b>UCMTCPCI_PORT_CONTROLLER_ALERT_DATA</b> structure.
                
            
        Call this function before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ucmtcpciportcontroller/nf-ucmtcpciportcontroller-ucmtcpciportcontrolleralert">UcmTcpciPortControllerAlert</a>.


## -parameters




### -param AlertData [out]

A pointer to the driver-allocated <b>UCMTCPCI_PORT_CONTROLLER_ALERT_DATA</b> structure.


