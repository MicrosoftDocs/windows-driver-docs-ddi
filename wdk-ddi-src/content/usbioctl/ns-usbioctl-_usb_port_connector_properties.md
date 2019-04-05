---
UID: NS:usbioctl._USB_PORT_CONNECTOR_PROPERTIES
title: _USB_PORT_CONNECTOR_PROPERTIES (usbioctl.h)
description: The USB_PORT_CONNECTOR_PROPERTIES structure is used with the IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES I/O control request to retrieve information about a port on a particular SuperSpeed hub.
old-location: buses\usb_port_connector_properties.htm
tech.root: usbref
ms.assetid: 93818067-A7EC-4796-B80F-75ADD6315ADF
ms.date: 05/07/2018
ms.keywords: "*PUSB_PORT_CONNECTOR_PROPERTIES, PUSB_PORT_CONNECTOR_PROPERTIES, PUSB_PORT_CONNECTOR_PROPERTIES structure pointer [Buses], USB_PORT_CONNECTOR_PROPERTIES, USB_PORT_CONNECTOR_PROPERTIES structure [Buses], _USB_PORT_CONNECTOR_PROPERTIES, buses.usb_port_connector_properties, usbioctl/PUSB_PORT_CONNECTOR_PROPERTIES, usbioctl/USB_PORT_CONNECTOR_PROPERTIES"
ms.topic: struct
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: None supported
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Usbioctl.h
api_name:
- USB_PORT_CONNECTOR_PROPERTIES
product:
- Windows
targetos: Windows
req.typenames: USB_PORT_CONNECTOR_PROPERTIES, *PUSB_PORT_CONNECTOR_PROPERTIES
---

# _USB_PORT_CONNECTOR_PROPERTIES structure


## -description


The <b>USB_PORT_CONNECTOR_PROPERTIES</b> structure is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450863">IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES</a> I/O control request to retrieve information about a port on a particular SuperSpeed hub.


## -struct-fields




### -field ConnectionIndex

The port number being queried in the request. <b>ConnectionIndex</b> is specified by the caller. If there are <i>n</i> ports on the SuperSpeed hub, the ports are numbered from 1 to <i>n</i>. To get the number of ports, the caller first sends an <a href="https://msdn.microsoft.com/library/windows/hardware/hh450860">IOCTL_USB_GET_HUB_INFORMATION_EX</a> I/O control request. The request retrieves the highest port number on the hub.


### -field ActualLength

The number of bytes required to hold the entire <b>USB_PORT_CONNECTOR_PROPERTIES</b>
    structure including the string that contains the symbolic link name of the companion hub. That string is stored in the <b>CompanionHubSymbolicLinkName</b> member. The <b>ActualLength</b> value is returned by the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450863">IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES</a> request and used by the caller to allocate a buffer to hold the received information. For details, see <b>IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES</b>. 


### -field UsbPortProperties

The port properties. Upon completion of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450863">IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES</a> request, <b>UsbPortProperties</b> contains a bitwise <b>OR</b> of one or more flags indicating the properties and capabilities of the port. The flags are defined in <a href="https://msdn.microsoft.com/library/windows/hardware/hh406266">USB_PORT_PROPERTIES</a>.


### -field CompanionIndex

The index of the companion port that is associated with the port being queried (specified by <b>ConnectionIndex</b>). If there are <i>n</i> companion ports, those ports are indexed from 0 to <i>n</i>–1.

If a port is mapped to more than one companion port, <b>CompanionIndex</b> is incremented on multiple queries to enumerate all companion ports.

For SuperSpeed hubs and xHCI controllers, <b>CompanionIndex</b> is always 0. For more information, see Remarks.


### -field CompanionPortNumber

The port number of the companion port that is given by <b>CompanionIndex</b>. If the port being queried shares a USB connector with a port on another hub,  <b>CompanionPortNumber</b> indicates the port number of the port on the other hub. 

<div class="alert"><b>Note</b>  For root hub of an xHCI controller, the shared port might be on the same hub.</div>
<div> </div>

### -field CompanionHubSymbolicLinkName

The Unicode string that contains the symbolic link  of the companion hub that shares the USB connector. If a companion hub exists, <b>CompanionPortNumber</b> is nonzero. Otherwise, <b>CompanionHubSymbolicLinkName [0]</b> is <b>NULL</b>.


## -remarks



A SuperSpeed 3.0 hub contains two independent hub implementations.  One is for USB 2.0 devices, and the hub implementation is similar to existing 2.0 hubs.  The other hub is only for SuperSpeed devices.  Because the USB 2.0 and 3.0 bus signaling are electrically independent, both of those hubs operate simultaneously.  Therefore, when a SuperSpeed hub is connected to the host, Windows enumerates the two hubs independently;  one hub is associated with a USB 2.0 port, and the other hub with a USB 3.0 port.  Each hub has its downstream and upstream ports. USB physical  connectors are shared between ports that are associated with  those two hub implementations. 

 Similarly,  an xHCI controller must be able to handle SuperSpeed, high-speed, full-speed, and low-speed devices. The USB 3.0 specification requires an xHCI controller to  contain two independent execution units each for USB 3.0 and USB 2.0 bus speeds. The USB 3.0 execution unit handles SuperSpeed traffic on the bus. The USB 2.0 execution unit must handle low, full, and high speed traffic. That requirement can be met in many ways. For instance, in one implementation, the USB 2.0 execution unit can have either a downstream USB 1.1 execution unit or a downstream USB 2.0 hub. The other execution unit handles SuperSpeed traffic on the bus. For instance, in one implementation, the xHCI controller can have a downstream USB 2.0 hub (instead of a USB 2.0 host controller) with a transaction translator to handle full-speed and low-speed traffic. That downstream hub shares connectors with the ports of the SuperSpeed root hub.

  In cases where USB connectors are shared, the port that is being queried through the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450863">IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES</a> I/O control request is specified by <b>ConnectionIndex</b>, and the port that shares the connector is called the <i>companion port</i>. Upon completion of the request, the <b>CompanionIndex</b>, <b>CompanionPortNumber</b>, and <b>CompanionHubSymbolicLinkName</b> members of <b>USB_PORT_CONNECTOR_PROPERTIES</b> can be used to determine the port routing in those cases.

If more than one companion port is associated with the port that is being queried, the application can get information about all companion ports by sending the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450863">IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES</a> I/O control request in a loop and incrementing the <b>CompanionIndex</b> value in each iteration. When all of the ports have been enumerated and there is no  port associated with the index specified in <b>CompanionIndex</b>, the request completes successfully, <b>CompanionPortNumber</b> is set to 0, and <b>CompanionHubSymbolicLinkName</b> is NULL.

To get information about the operating speed of a device attached to a particular port, the application can send the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450861">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2</a> I/O control request.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh450861">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450863">IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406262">USB_HUB_INFORMATION_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406265">USB_PORT_CONNECTOR_PROPERTIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406266">USB_PORT_PROPERTIES</a>
 

 

