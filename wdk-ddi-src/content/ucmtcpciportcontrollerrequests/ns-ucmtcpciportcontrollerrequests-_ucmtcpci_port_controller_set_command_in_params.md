---
UID: NS:ucmtcpciportcontrollerrequests._UCMTCPCI_PORT_CONTROLLER_SET_COMMAND_IN_PARAMS
title: "_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND_IN_PARAMS"
author: windows-driver-content
description: Stores the specified command registers. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND request.
old-location: buses\ucmtcpci_port_controller_set_command_in_params.htm
old-project: usbref
ms.assetid: 0c41328d-a40a-4b76-a738-5e255aba7f58
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: UCMTCPCI_PORT_CONTROLLER_SET_COMMAND_IN_PARAMS structure [Buses], _UCMTCPCI_PORT_CONTROLLER_SET_COMMAND_IN_PARAMS, UCMTCPCI_PORT_CONTROLLER_SET_COMMAND_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_SET_COMMAND_IN_PARAMS, buses.ucmtcpci_port_controller_set_command_in_params, ucmtcpciportcontrollerrequests/PUCMTCPCI_PORT_CONTROLLER_SET_COMMAND_IN_PARAMS, PUCMTCPCI_PORT_CONTROLLER_SET_COMMAND_IN_PARAMS structure pointer [Buses], ucmtcpciportcontrollerrequests/UCMTCPCI_PORT_CONTROLLER_SET_COMMAND_IN_PARAMS, PUCMTCPCI_PORT_CONTROLLER_SET_COMMAND_IN_PARAMS
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
-	UcmTcpciPortControllerRequests.h
apiname:
-	UCMTCPCI_PORT_CONTROLLER_SET_COMMAND_IN_PARAMS
product: Windows
targetos: Windows
req.typenames: "*PUCMTCPCI_PORT_CONTROLLER_SET_COMMAND_IN_PARAMS, UCMTCPCI_PORT_CONTROLLER_SET_COMMAND_IN_PARAMS"
req.product: Windows 10 or later.
---

# _UCMTCPCI_PORT_CONTROLLER_SET_COMMAND_IN_PARAMS structure


## -description



             Stores the specified command registers. This structure is used in the <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_command.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND</a> request.
                 


## -syntax


````
typedef struct _UCMTCPCI_PORT_CONTROLLER_SET_COMMAND_IN_PARAMS {
  UCMTCPCIPORTCONTROLLER           PortControllerObject;
  UCMTCPCI_PORT_CONTROLLER_COMMAND Command;
} UCMTCPCI_PORT_CONTROLLER_SET_COMMAND_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_SET_COMMAND_IN_PARAMS;
````


## -struct-fields




#### - PortControllerObject

Handle to the port controller object that the client driver received in the previous call to <a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate.md">UcmTcpciPortControllerCreate</a>.


#### - Command


                     
                     A <b>UCMTCPCI_PORT_CONTROLLER_COMMAND</b>-value that 
                 indicates the type of control register. This enumeration is declared in UcmTcpciSpec.h.


## -see-also

<a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_set_command.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_SET_COMMAND</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCMTCPCI_PORT_CONTROLLER_SET_COMMAND_IN_PARAMS structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

