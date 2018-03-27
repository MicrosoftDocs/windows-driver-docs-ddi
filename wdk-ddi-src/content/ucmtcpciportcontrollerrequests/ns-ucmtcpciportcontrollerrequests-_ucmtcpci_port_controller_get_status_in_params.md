---
UID: NS:ucmtcpciportcontrollerrequests._UCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS
title: "_UCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS"
author: windows-driver-content
description: This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS request.
old-location: buses\ucmtcpci_port_controller_get_status_in_params.htm
old-project: usbref
ms.assetid: 1b57413b-e1cf-4ec4-80f4-aedffc015b46
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS, PUCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS, PUCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS structure pointer [Buses], UCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS, UCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS structure [Buses], _UCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS, buses.ucmtcpci_port_controller_get_status_in_params, ucmtcpciportcontrollerrequests/PUCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS, ucmtcpciportcontrollerrequests/UCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS"
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
-	UcmTcpciPortControllerRequests.h
api_name:
-	UCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS
product: Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS
req.product: Windows 10 or later.
---

# _UCMTCPCI_PORT_CONTROLLER_GET_STATUS_IN_PARAMS structure


## -description



             
             This structure is used in the 
             <a href="https://msdn.microsoft.com/library/windows/hardware/mt805833">IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS</a>  request.
         




## -struct-fields




### -field PortControllerObject

Handle to the port controller object that the client driver received in the previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt805844">UcmTcpciPortControllerCreate</a>.

