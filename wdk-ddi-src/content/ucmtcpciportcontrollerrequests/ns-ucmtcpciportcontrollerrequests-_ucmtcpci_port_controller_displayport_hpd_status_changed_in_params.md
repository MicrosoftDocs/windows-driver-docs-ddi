---
UID: NS:ucmtcpciportcontrollerrequests._UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED_IN_PARAMS
title: "_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED_IN_PARAMS"
author: windows-driver-content
description: Stores information about hot plug detect status of the DisplayPort connection. This structure is used in the IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED request.
old-location: buses\ucmtcpci_port_controller_displayport_hpd_status_changed_in_params.htm
old-project: usbref
ms.assetid: EFADE026-190C-4247-9452-0BE25D8279D8
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED_IN_PARAMS, PUCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED_IN_PARAMS, PUCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED_IN_PARAMS structure pointer [Buses], UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED_IN_PARAMS, UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED_IN_PARAMS structure [Buses], _UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED_IN_PARAMS, buses.ucmtcpci_port_controller_displayport_hpd_status_changed_in_params, ucmtcpciportcontrollerrequests/PUCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED_IN_PARAMS, ucmtcpciportcontrollerrequests/UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED_IN_PARAMS"
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
-	UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED_IN_PARAMS
product: Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED_IN_PARAMS
req.product: Windows 10 or later.
---

# _UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED_IN_PARAMS structure


## -description


Stores information about hot plug detect status of the DisplayPort connection. This structure is used in the 
             <a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_displayport_hpd_status_changed.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED</a>  request. 


## -syntax


````
typedef struct _UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED_IN_PARAMS {
  UCMTCPCIPORTCONTROLLER                          PortControllerObject;
  UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS HPDStatus;
} UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED_IN_PARAMS, *PUCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED_IN_PARAMS;
````


## -struct-fields




### -field PortControllerObject

Handle to the port controller object that the client driver received in the previous call to <a href="..\ucmtcpciportcontroller\nf-ucmtcpciportcontroller-ucmtcpciportcontrollercreate.md">UcmTcpciPortControllerCreate</a>.


### -field HPDStatus

A <a href="..\ucmtcpciportcontrollerrequests\ne-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_displayport_hpd_status.md">UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS</a>-type value that indicates status.


## -see-also

<a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_displayport_hpd_status_changed.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED</a>



 

 


