---
UID: NE:usbioctl._USB_CONNECTION_STATUS
title: _USB_CONNECTION_STATUS (usbioctl.h)
description: The USB_CONNECTION_STATUS enumerator indicates the status of the connection to a device on a USB hub port.
old-location: buses\usb_connection_status.htm
tech.root: usbref
ms.assetid: 9006f74f-4033-4f07-816c-380d6d8b3a2d
ms.date: 05/07/2018
keywords: ["_USB_CONNECTION_STATUS enumeration"]
ms.keywords: "*PUSB_CONNECTION_STATUS, DeviceCausedOvercurrent, DeviceConnected, DeviceEnumerating, DeviceFailedEnumeration, DeviceGeneralFailure, DeviceHubNestedTooDeeply, DeviceInLegacyHub, DeviceNotEnoughBandwidth, DeviceNotEnoughPower, DeviceReset, NoDeviceConnected, PUSB_CONNECTION_STATUS, PUSB_CONNECTION_STATUS enumeration pointer [Buses], USB_CONNECTION_STATUS, USB_CONNECTION_STATUS enumeration [Buses], _USB_CONNECTION_STATUS, buses.usb_connection_status, usbioctl/DeviceCausedOvercurrent, usbioctl/DeviceConnected, usbioctl/DeviceEnumerating, usbioctl/DeviceFailedEnumeration, usbioctl/DeviceGeneralFailure, usbioctl/DeviceHubNestedTooDeeply, usbioctl/DeviceInLegacyHub, usbioctl/DeviceNotEnoughBandwidth, usbioctl/DeviceNotEnoughPower, usbioctl/DeviceReset, usbioctl/NoDeviceConnected, usbioctl/PUSB_CONNECTION_STATUS, usbioctl/USB_CONNECTION_STATUS, usbstrct_3f747b8b-9fe5-48f1-bfc4-3701ab8be8e9.xml"
f1_keywords:
 - "usbioctl/USB_CONNECTION_STATUS"
 - "USB_CONNECTION_STATUS"
req.header: usbioctl.h
req.include-header: Usbioctl.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- usbioctl.h
api_name:
- USB_CONNECTION_STATUS
product:
- Windows
targetos: Windows
req.typenames: USB_CONNECTION_STATUS, *PUSB_CONNECTION_STATUS
---

# _USB_CONNECTION_STATUS enumeration


## -description


The <b>USB_CONNECTION_STATUS</b> enumerator indicates the status of the connection to a device on a USB hub port.


## -enum-fields




### -field NoDeviceConnected

Indicates that there is no device connected to the port.


### -field DeviceConnected

Indicates that a device was successfully connected to the port.


### -field DeviceFailedEnumeration

Indicates that an attempt was made to connect a device to the port, but the enumeration of the device failed.


### -field DeviceGeneralFailure

Indicates that an attempt was made to connect a device to the port, but the connection failed for unspecified reasons.


### -field DeviceCausedOvercurrent

Indicates that an attempt was made to connect a device to the port, but the attempt failed because of an overcurrent condition.


### -field DeviceNotEnoughPower

Indicates that an attempt was made to connect a device to the port, but there was not enough power to drive the device, and the connection failed.


### -field DeviceNotEnoughBandwidth

Indicates that an attempt was made to connect a device to the port, but there was not enough bandwidth available for the device to function properly, and the connection failed.


### -field DeviceHubNestedTooDeeply

Indicates that an attempt was made to connect a device to the port, but the nesting of USB hubs was too deep, so the connection failed. 


### -field DeviceInLegacyHub

Indicates that an attempt was made to connect a device to the port of an unsupported legacy hub, and the connection failed.


### -field DeviceEnumerating

Indicates that a device connected to the port is currently being enumerated.  

<b>Note</b>  This constant is supported in Windows Vista and later operating systems.


### -field DeviceReset

Indicates that device connected to the port is currently being reset.  

<b>Note</b>  This constant is supported in Windows Vista and later operating systems.


## -remarks



The USB bus driver reports connection status in a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_node_connection_information_ex">USB_NODE_CONNECTION_INFORMATION_EX</a> structure in response to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_node_connection_information_ex">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX</a> request.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_node_connection_information_ex">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_usbref/#enumerations">USB Constants and Enumerations</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_node_connection_information_ex">USB_NODE_CONNECTION_INFORMATION_EX</a>
 

 

