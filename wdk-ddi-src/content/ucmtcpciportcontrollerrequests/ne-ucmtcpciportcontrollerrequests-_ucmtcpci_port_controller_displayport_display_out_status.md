---
UID: NE:ucmtcpciportcontrollerrequests._UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_DISPLAY_OUT_STATUS
title: "_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_DISPLAY_OUT_STATUS"
author: windows-driver-content
description: Defines values to determine whether a display out status for a DisplayPort device is enabled.
old-location: buses\_ucmtcpci_port_controller_displayport_display_out_status.htm
old-project: UsbRef
ms.assetid: c57da7f2-d484-479c-9d8a-626789d8b23e
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: ",  , ,, A, C, D, E, I, L, M, N, O, P, R, S, T, U, UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_DISPLAY_OUT_STATUS, UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_DISPLAY_OUT_STATUS enumeration [Buses], UcmTcpciPortControllerDisplayOutStatusOff, UcmTcpciPortControllerDisplayOutStatusOn, Y, _, _UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_DISPLAY_OUT_STATUS, buses._ucmtcpci_port_controller_displayport_display_out_status, ucmtcpciportcontrollerrequests/UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_DISPLAY_OUT_STATUS, ucmtcpciportcontrollerrequests/UcmTcpciPortControllerDisplayOutStatusOff, ucmtcpciportcontrollerrequests/UcmTcpciPortControllerDisplayOutStatusOn"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Ucmtcpciportcontrollerrequests.h
apiname:
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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_DISPLAY_OUT_STATUS enumeration%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

