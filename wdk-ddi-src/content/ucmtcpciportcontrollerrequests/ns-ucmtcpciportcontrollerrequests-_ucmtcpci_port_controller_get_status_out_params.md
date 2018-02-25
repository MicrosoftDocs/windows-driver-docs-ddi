---
UID: NS:ucmtcpciportcontrollerrequests._UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS
title: "_UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS"
author: windows-driver-content
description: Stores the values of all status registers of the port controller. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS request.
old-location: buses\ucmtcpci_port_controller_get_status_out_params.htm
old-project: UsbRef
ms.assetid: e43b2a10-20b5-4cb8-ae7b-fc1feb7a4bf1
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ",  , *, *PUCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS, ,, A, C, E, G, I, L, M, N, O, P, PUCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS, PUCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS structure pointer [Buses], R, S, T, U, UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS, UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS structure [Buses], _, _UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS, buses.ucmtcpci_port_controller_get_status_out_params, ucmtcpciportcontrollerrequests/PUCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS, ucmtcpciportcontrollerrequests/UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ucmtcpciportcontrollerrequests.h
apiname:
-	UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS
product: Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS
req.product: Windows 10 or later.
---

# _UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS structure


## -description



             Stores the values of all status registers of the port controller. This structure is used in the 
             <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_get_status.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS</a> request.


## -syntax


````
typedef struct _UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS {
  UCMTCPCI_PORT_CONTROLLER_CC_STATUS    CCStatus;
  UCMTCPCI_PORT_CONTROLLER_POWER_STATUS PowerStatus;
  UCMTCPCI_PORT_CONTROLLER_FAULT_STATUS FaultStatus;
} UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS;
````


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

<a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_get_status.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_STATUS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20UCMTCPCI_PORT_CONTROLLER_GET_STATUS_OUT_PARAMS structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

