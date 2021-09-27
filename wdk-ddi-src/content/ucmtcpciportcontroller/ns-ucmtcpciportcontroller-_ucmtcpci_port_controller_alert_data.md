---
UID: NS:ucmtcpciportcontroller._UCMTCPCI_PORT_CONTROLLER_ALERT_DATA
title: _UCMTCPCI_PORT_CONTROLLER_ALERT_DATA (ucmtcpciportcontroller.h)
description: Contains information about hardware alerts received on the port controller object. This structure is used in the UcmTcpciPortControllerAlert call. Call UCMTCPCI_PORT_CONTROLLER_ALERT_DATA_INIT to initialize this structure.
old-location: buses\ucmtcpci_port_controller_alert_data.htm
tech.root: usbref
ms.date: 09/14/2021
keywords: ["UCMTCPCI_PORT_CONTROLLER_ALERT_DATA structure"]
ms.keywords: "*PUCMTCPCI_PORT_CONTROLLER_ALERT_DATA, PUCMTCPCI_PORT_CONTROLLER_ALERT_DATA, PUCMTCPCI_PORT_CONTROLLER_ALERT_DATA structure pointer [Buses], UCMTCPCI_PORT_CONTROLLER_ALERT_DATA, UCMTCPCI_PORT_CONTROLLER_ALERT_DATA structure [Buses], _UCMTCPCI_PORT_CONTROLLER_ALERT_DATA, buses.ucmtcpci_port_controller_alert_data, ucmtcpciportcontroller/PUCMTCPCI_PORT_CONTROLLER_ALERT_DATA, ucmtcpciportcontroller/UCMTCPCI_PORT_CONTROLLER_ALERT_DATA"
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
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_ALERT_DATA, *PUCMTCPCI_PORT_CONTROLLER_ALERT_DATA
f1_keywords:
 - _UCMTCPCI_PORT_CONTROLLER_ALERT_DATA
 - ucmtcpciportcontroller/_UCMTCPCI_PORT_CONTROLLER_ALERT_DATA
 - PUCMTCPCI_PORT_CONTROLLER_ALERT_DATA
 - ucmtcpciportcontroller/PUCMTCPCI_PORT_CONTROLLER_ALERT_DATA
 - UCMTCPCI_PORT_CONTROLLER_ALERT_DATA
 - ucmtcpciportcontroller/UCMTCPCI_PORT_CONTROLLER_ALERT_DATA
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ucmtcpciportcontroller.h
api_name:
 - _UCMTCPCI_PORT_CONTROLLER_ALERT_DATA
 - PUCMTCPCI_PORT_CONTROLLER_ALERT_DATA
 - UCMTCPCI_PORT_CONTROLLER_ALERT_DATA
---

# _UCMTCPCI_PORT_CONTROLLER_ALERT_DATA structure

## -description

Contains information about hardware alerts received on the port controller object. This structure is used in the [UcmTcpciPortControllerAlert](/windows-hardware/drivers/ddi/ucmtcpciportcontroller/nf-ucmtcpciportcontroller-ucmtcpciportcontrolleralert) call. Call [UCMTCPCI_PORT_CONTROLLER_ALERT_DATA_INIT](/windows-hardware/drivers/ddi/ucmtcpciportcontroller/nf-ucmtcpciportcontroller-ucmtcpci_port_controller_alert_data_init) to initialize this structure.

## -struct-fields

### -field Size

Size of this structure.

### -field AlertType

A [UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE](/windows-hardware/drivers/ddi/ucmtcpciportcontroller/ne-ucmtcpciportcontroller-_ucmtcpci_port_controller_alert_type) value that indicates the type of hardware alert.

### -field CCStatus

A **UCMTCPCI_PORT_CONTROLLER_CC_STATUS** structure that contains status information about the CC lines of the port controller. This structure is defined in UcmTcpciSpec.h.

### -field PowerStatus

A **UCMTCPCI_PORT_CONTROLLER_POWER_STATUS** structure that contains the power status of the port controller. This structure is defined in UcmTcpciSpec.h.

### -field FaultStatus

A **UCMTCPCI_PORT_CONTROLLER_FAULT_STATUS** structure that contains the fault status of the port controller. This structure is defined in UcmTcpciSpec.h.

### -field ReceiveBuffer

A pointer to a **UCMTCPCI_PORT_CONTROLLER_RECEIVE_BUFFER** structure that represents the buffer for receiving the alert from the port controller. This structure is defined in UcmTcpciSpec.h.

## -see-also

[UcmTcpciPortControllerAlert](/windows-hardware/drivers/ddi/ucmtcpciportcontroller/nf-ucmtcpciportcontroller-ucmtcpciportcontrolleralert)
