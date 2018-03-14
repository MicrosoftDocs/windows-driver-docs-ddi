---
UID: NE:ucmtcpciportcontrollerrequests._UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_DISPLAY_OUT_STATUS
title: "_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_DISPLAY_OUT_STATUS"
author: windows-driver-content
description: Defines values to determine whether a display out status for a DisplayPort device is enabled.
old-location: buses\_ucmtcpci_port_controller_displayport_display_out_status.htm
old-project: usbref
ms.assetid: c57da7f2-d484-479c-9d8a-626789d8b23e
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_DISPLAY_OUT_STATUS, UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_DISPLAY_OUT_STATUS enumeration [Buses], UcmTcpciPortControllerDisplayOutStatusOff, UcmTcpciPortControllerDisplayOutStatusOn, _UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_DISPLAY_OUT_STATUS, buses._ucmtcpci_port_controller_displayport_display_out_status, ucmtcpciportcontrollerrequests/UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_DISPLAY_OUT_STATUS, ucmtcpciportcontrollerrequests/UcmTcpciPortControllerDisplayOutStatusOff, ucmtcpciportcontrollerrequests/UcmTcpciPortControllerDisplayOutStatusOn
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ucmtcpciportcontrollerrequests.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Ucmtcpciportcontrollerrequests.h
api_name:
-	UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_DISPLAY_OUT_STATUS
product: Windows
targetos: Windows
req.typenames: UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_DISPLAY_OUT_STATUS
req.product: Windows 10 or later.
---

# _UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_DISPLAY_OUT_STATUS enumeration


## -description


Defines values to determine whether a display out status for a DisplayPort device is enabled


## -syntax


````
typedef enum _UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_DISPLAY_OUT_STATUS { 
  UcmTcpciPortControllerDisplayOutStatusOff  = 0x0,
  UcmTcpciPortControllerDisplayOutStatusOn   = 0x1
} UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_DISPLAY_OUT_STATUS;
````


## -enum-fields




### -field UcmTcpciPortControllerDisplayOutStatusOff

Display out status is enabled.


### -field UcmTcpciPortControllerDisplayOutStatusOn

Display out status is enabled.


## -see-also

<a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_displayport_display_out_status_changed.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_DISPLAY_OUT_STATUS_CHANGED</a>



<a href="..\ucmtcpciportcontrollerrequests\ns-ucmtcpciportcontrollerrequests-_ucmtcpci_port_controller_displayport_display_out_status_changed_in_params.md">UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_DISPLAY_OUT_STATUS_CHANGED_IN_PARAMS</a>



 

 


