---
UID: NS:usbioctl._USB_NODE_CONNECTION_INFORMATION_EX
title: _USB_NODE_CONNECTION_INFORMATION_EX (usbioctl.h)
description: The USB_NODE_CONNECTION_INFORMATION_EX structure is used in conjunction with the IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX request to obtain information about the connection associated with the indicated USB port.
old-location: buses\usb_node_connection_information_ex.htm
tech.root: usbref
ms.assetid: d824e279-50a9-46a1-a93a-9ae17928f146
ms.date: 05/07/2018
keywords: ["USB_NODE_CONNECTION_INFORMATION_EX structure"]
ms.keywords: "*PUSB_NODE_CONNECTION_INFORMATION_EX, PUSB_NODE_CONNECTION_INFORMATION_EX, PUSB_NODE_CONNECTION_INFORMATION_EX structure pointer [Buses], USB_NODE_CONNECTION_INFORMATION_EX, USB_NODE_CONNECTION_INFORMATION_EX structure [Buses], _USB_NODE_CONNECTION_INFORMATION_EX, buses.usb_node_connection_information_ex, usbioctl/PUSB_NODE_CONNECTION_INFORMATION_EX, usbioctl/USB_NODE_CONNECTION_INFORMATION_EX, usbstrct_2ee693b4-4279-4f3a-bbfb-1855f9b917d6.xml"
f1_keywords:
 - "usbioctl/USB_NODE_CONNECTION_INFORMATION_EX"
 - "USB_NODE_CONNECTION_INFORMATION_EX"
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
- USB_NODE_CONNECTION_INFORMATION_EX
targetos: Windows
req.typenames: USB_NODE_CONNECTION_INFORMATION_EX, *PUSB_NODE_CONNECTION_INFORMATION_EX
---

# _USB_NODE_CONNECTION_INFORMATION_EX structure


## -description


The <b>USB_NODE_CONNECTION_INFORMATION_EX</b> structure is used in conjunction with the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_node_connection_information_ex">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX</a> request to obtain information about the connection associated with the indicated USB port.


## -struct-fields




### -field ConnectionIndex

Contains a value greater than or equal to 1 that specifies the number of the port.


### -field DeviceDescriptor

Contains a structure of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_device_descriptor">USB_DEVICE_DESCRIPTOR</a> that reports the USB device descriptor returned by the attached device during enumeration.


### -field CurrentConfigurationValue

Contains the ID used with the SetConfiguration request to specify that current configuration of the device connected to the indicated port. For an explanation of this value, see section 9.4.7 in the Universal Serial Bus 3.1 Specification available at [USB Document Library](https://www.usb.org/documents).


### -field Speed

Contains a value of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbspec/ne-usbspec-_usb_device_speed">USB_DEVICE_SPEED</a> that indicates the speed of the device. 


### -field DeviceIsHub

Indicates, when <b>TRUE</b>, that the device attached to the port is a hub.


### -field DeviceAddress

Contains the USB-assigned, bus-relative address of the device that is attached to the port.


### -field NumberOfOpenPipes

Indicates the number of open USB pipes associated with the port.


### -field ConnectionStatus

Contains an enumerator of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ne-usbioctl-_usb_connection_status">USB_CONNECTION_STATUS</a> that indicates the connection status.


### -field PipeList

Contains an array of structures of type <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_pipe_info">USB_PIPE_INFO</a> that describes the open pipes associated with the port. Pipe descriptions include the schedule offset of the pipe and the associated endpoint descriptor. This information can be used to calculate bandwidth usage.


## -remarks



If there is no device connected, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_node_connection_information_ex">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX</a> just returns information about the port. If a device is connected to the port <b>IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX</b> returns information about both the port and the connected device.

The <b>USB_NODE_CONNECTION_INFORMATION_EX</b> structure is an extended version of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_node_connection_information">USB_NODE_CONNECTION_INFORMATION</a>. The two structures are identical, except for one member. In the extended structure, the <b>Speed</b> member indicates the device speed.  

The <b>Speed</b> member of the <b>USB_NODE_CONNECTION_INFORMATION_EX</b> structure is a UCHAR and it can specify any of the values of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbspec/ne-usbspec-_usb_device_speed">USB_DEVICE_SPEED</a> enumerator.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">USB Structures</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ne-usbioctl-_usb_connection_status">USB_CONNECTION_STATUS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_pipe_info">USB_PIPE_INFO</a>
 

 

