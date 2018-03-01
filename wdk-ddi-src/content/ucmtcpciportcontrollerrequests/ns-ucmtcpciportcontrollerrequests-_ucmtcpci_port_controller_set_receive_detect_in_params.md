---
UID: NS:ucmtcpciportcontrollerrequests._UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT_IN_PARAMS
title: "_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT_IN_PARAMS"
author: windows-driver-content
description: Stores the value of the RECEIVE_DETECT Register. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT request.
old-location: buses\ucmtcpci_port_controller_set_receive_detect_in_params.htm
old-project: usbref
ms.assetid: 2a33613b-e3f5-47e0-b05e-0427a0fb3c58
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT_IN_PARAMS, PUCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT_IN_PARAMS, PUCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT_IN_PARAMS structure pointer [Buses], UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT_IN_PARAMS, UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT_IN_PARAMS structure [Buses], _UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT_IN_PARAMS, buses.ucmtcpci_port_controller_set_receive_detect_in_params, ucmtcpciportcontrollerrequests/PUCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT_IN_PARAMS, ucmtcpciportcontrollerrequests/UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT_IN_PARAMS"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT_IN_PARAMS
product: Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT_IN_PARAMS
req.product: Windows 10 or later.
---

# _UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT_IN_PARAMS structure


## -description



             Stores the value of the RECEIVE_DETECT Register. This structure is used in the <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_receive_detect.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT</a> request.
                 


## -syntax


````
typedef struct _UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT_IN_PARAMS {
  UCMTCPCIPORTCONTROLLER                  PortControllerObject;
  UCMTCPCI_PORT_CONTROLLER_RECEIVE_DETECT ReceiveDetect;
} UCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_SET_RECEIVE_DETECT_IN_PARAMS;
````


## -struct-fields




### -field PortControllerObject

Handle to the port controller object that the client driver received in the previous call to <a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate.md">UcmTcpciPortControllerCreate</a>.


### -field ReceiveDetect


                     A 
                 <b>UCMTCPCI_PORT_CONTROLLER_RECEIVE_DETECT</b> structure that describes the RECEIVE_DETECT Register defined as per the Universal Serial Bus Type-C Port Controller Interface Specification. This structure is declared in UcmTcpciSpec.h.

