---
UID: NE:ucmtcpciportcontrollerrequests._UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS
title: _UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS
author: windows-driver-content
description: Defines values to determine whether a DisplayPort device is plugged in.
old-location: buses\ucmtcpci_port_controller_displayport_hpd_status.htm
old-project: usbref
ms.assetid: 6BE5948B-DAC9-4448-AE22-108805BB364C
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS, UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ucmtcpciportcontrollerrequests.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS
req.alt-loc: Ucmtcpciportcontrollerrequests.h
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
req.typenames: UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS
req.product: Windows 10 or later.
---

# _UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS enumeration



## -description
Defines values to determine whether a DisplayPort device is plugged in.



## -syntax

````
typedef enum _UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS { 
  UcmTcpciPortControllerHPDStatusLow   = 0x1,
  UcmTcpciPortControllerHPDStatusHigh  = 0x2
} UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS;
````


## -enum-fields

### -field UcmTcpciPortControllerHPDStatusLow

The DisplayPort device is unplugged.


### -field UcmTcpciPortControllerHPDStatusHigh

A DisplayPort device such as a monitor is plugged in.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\ucmtcpciportcontrollerrequests\ni-ucmtcpciportcontrollerrequests-ioctl_ucmtcpci_port_controller_displayport_hpd_status_changed.md">IOCTL_UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS_CHANGED</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCMTCPCI_PORT_CONTROLLER_DISPLAYPORT_HPD_STATUS enumeration%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

