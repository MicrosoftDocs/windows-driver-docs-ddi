---
UID: NS:ucmtcpciportcontrollerrequests._UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS
title: "_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS"
author: windows-driver-content
description: This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL request.
old-location: buses\ucmtcpci_port_controller_get_control_in_params.htm
old-project: UsbRef
ms.assetid: 93581775-f523-4e3b-bd90-13ad6e12480e
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: PUCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS structure pointer [Buses], PUCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS, UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS structure [Buses], ucmtcpciportcontrollerrequests/PUCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS, UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS, _UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS, ucmtcpciportcontrollerrequests/UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS, buses.ucmtcpci_port_controller_get_control_in_params
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
-	UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS
product: Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS
req.product: Windows 10 or later.
---

# _UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS structure


## -description



             This structure is used in the 
             <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_get_control.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL</a>  request.
         


## -syntax


````
typedef struct _UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS {
  UCMTCPCIPORTCONTROLLER PortControllerObject;
} UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS;
````


## -struct-fields




### -field PortControllerObject

Handle to the port controller object that the client driver received in the previous call to <a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate.md">UcmTcpciPortControllerCreate</a>.


## -see-also

<a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_get_control.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_GET_CONTROL</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20UCMTCPCI_PORT_CONTROLLER_GET_CONTROL_IN_PARAMS structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

