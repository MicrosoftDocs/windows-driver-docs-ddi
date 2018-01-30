---
UID: NS:ucmtcpciportcontroller._UCMTCPCI_PORT_CONTROLLER_ALERT_DATA
title: "_UCMTCPCI_PORT_CONTROLLER_ALERT_DATA"
author: windows-driver-content
description: Contains information about hardware alerts received on the port controller object. This structure is used in the UcmTcpciPortControllerAlert call. Call UCMTCPCI_PORT_CONTROLLER_ALERT_DATA_INIT to initialize this structure.
old-location: buses\ucmtcpci_port_controller_alert_data.htm
old-project: usbref
ms.assetid: 4b3c2fc8-d7c3-4223-a88e-5db9ad852618
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ucmtcpciportcontroller/PUCMTCPCI_PORT_CONTROLLER_ALERT_DATA, *PUCMTCPCI_PORT_CONTROLLER_ALERT_DATA, PUCMTCPCI_PORT_CONTROLLER_ALERT_DATA structure pointer [Buses], PUCMTCPCI_PORT_CONTROLLER_ALERT_DATA, ucmtcpciportcontroller/UCMTCPCI_PORT_CONTROLLER_ALERT_DATA, buses.ucmtcpci_port_controller_alert_data, UCMTCPCI_PORT_CONTROLLER_ALERT_DATA structure [Buses], UCMTCPCI_PORT_CONTROLLER_ALERT_DATA, _UCMTCPCI_PORT_CONTROLLER_ALERT_DATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ucmtcpciportcontroller.h
apiname:
-	UCMTCPCI_PORT_CONTROLLER_ALERT_DATA
product: Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_ALERT_DATA, *PUCMTCPCI_PORT_CONTROLLER_ALERT_DATA
req.product: Windows 10 or later.
---

# _UCMTCPCI_PORT_CONTROLLER_ALERT_DATA structure


## -description



                 Contains information about hardware alerts received on the port controller object. This structure is used in the <a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpciportcontrolleralert.md">UcmTcpciPortControllerAlert</a> call. Call <a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpci_port_controller_alert_data_init.md">UCMTCPCI_PORT_CONTROLLER_ALERT_DATA_INIT</a> to initialize this structure.
             


## -syntax


````
typedef struct _UCMTCPCI_PORT_CONTROLLER_ALERT_DATA {
  ULONG                               Size;
  UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE AlertType;
  union {
    UCMTCPCI_PORT_CONTROLLER_CC_STATUS       CCStatus;
    UCMTCPCI_PORT_CONTROLLER_POWER_STATUS    PowerStatus;
    UCMTCPCI_PORT_CONTROLLER_FAULT_STATUS    FaultStatus;
    PUCMTCPCI_PORT_CONTROLLER_RECEIVE_BUFFER ReceiveBuffer;
  };
} UCMTCPCI_PORT_CONTROLLER_ALERT_DATA, *PUCMTCPCI_PORT_CONTROLLER_ALERT_DATA;
````


## -struct-fields




### -field CCStatus

A 
                     <b>UCMTCPCI_PORT_CONTROLLER_CC_STATUS</b> structure that contains status information about the CC lines of the port controller.
                 This structure is defined in UcmTcpciSpec.h.


### -field PowerStatus

A 
                     <b>UCMTCPCI_PORT_CONTROLLER_POWER_STATUS</b> structure that contains the power status of the port controller.
                 This structure is defined in UcmTcpciSpec.h.


### -field FaultStatus

A 
                     <b>UCMTCPCI_PORT_CONTROLLER_FAULT_STATUS</b> structure that contains the fault status of the port controller.
                 This structure is defined in UcmTcpciSpec.h.


### -field ReceiveBuffer


                     A pointer to a 
                 <a href="https://msdn.microsoft.com/d051efa0-b637-41d8-935f-0d6e2e7eeca6">UCMTCPCI_PORT_CONTROLLER_RECEIVE_BUFFER</a> structure that represents the buffer for receiving the alert from the port controller. This structure is defined in UcmTcpciSpec.h.


### -field Size

Size of this structure.
                     
                 


### -field AlertType

A <a href="..\ucmtcpciportcontroller\ne-ucmtcpciportcontroller-_ucmtcpci_port_controller_alert_type.md">UCMTCPCI_PORT_CONTROLLER_ALERT_TYPE</a> value that indicates the type of hardware alert.
                     
                 


## -see-also

<a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpciportcontrolleralert.md">UcmTcpciPortControllerAlert</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCMTCPCI_PORT_CONTROLLER_ALERT_DATA structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

