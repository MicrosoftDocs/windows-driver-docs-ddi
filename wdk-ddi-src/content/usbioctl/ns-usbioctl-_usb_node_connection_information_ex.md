---
UID: NS:usbioctl._USB_NODE_CONNECTION_INFORMATION_EX
title: "_USB_NODE_CONNECTION_INFORMATION_EX"
author: windows-driver-content
description: The USB_NODE_CONNECTION_INFORMATION_EX structure is used in conjunction with the IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX request to obtain information about the connection associated with the indicated USB port.
old-location: buses\usb_node_connection_information_ex.htm
old-project: usbref
ms.assetid: d824e279-50a9-46a1-a93a-9ae17928f146
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PUSB_NODE_CONNECTION_INFORMATION_EX, PUSB_NODE_CONNECTION_INFORMATION_EX, PUSB_NODE_CONNECTION_INFORMATION_EX structure pointer [Buses], USB_NODE_CONNECTION_INFORMATION_EX, USB_NODE_CONNECTION_INFORMATION_EX structure [Buses], _USB_NODE_CONNECTION_INFORMATION_EX, buses.usb_node_connection_information_ex, usbioctl/PUSB_NODE_CONNECTION_INFORMATION_EX, usbioctl/USB_NODE_CONNECTION_INFORMATION_EX, usbstrct_2ee693b4-4279-4f3a-bbfb-1855f9b917d6.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbioctl.h
api_name:
-	USB_NODE_CONNECTION_INFORMATION_EX
product: Windows
targetos: Windows
req.typenames: USB_NODE_CONNECTION_INFORMATION_EX, *PUSB_NODE_CONNECTION_INFORMATION_EX
req.product: Windows 10 or later.
---

# _USB_NODE_CONNECTION_INFORMATION_EX structure


## -description


The <b>USB_NODE_CONNECTION_INFORMATION_EX</b> structure is used in conjunction with the <a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_node_connection_information_ex.md">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX</a> request to obtain information about the connection associated with the indicated USB port.


## -syntax


````
typedef struct _USB_NODE_CONNECTION_INFORMATION_EX {
  ULONG                 ConnectionIndex;
  USB_DEVICE_DESCRIPTOR DeviceDescriptor;
  UCHAR                 CurrentConfigurationValue;
  UCHAR                 Speed;
  BOOLEAN               DeviceIsHub;
  USHORT                DeviceAddress;
  ULONG                 NumberOfOpenPipes;
  USB_CONNECTION_STATUS ConnectionStatus;
  USB_PIPE_INFO         PipeList[];
} USB_NODE_CONNECTION_INFORMATION_EX, *PUSB_NODE_CONNECTION_INFORMATION_EX;
````


## -struct-fields




### -field ConnectionIndex

Contains a value greater than or equal to 1 that specifies the number of the port.


### -field DeviceDescriptor

Contains a structure of type <a href="..\usbspec\ns-usbspec-_usb_device_descriptor.md">USB_DEVICE_DESCRIPTOR</a> that reports the USB device descriptor returned by the attached device during enumeration.


### -field CurrentConfigurationValue

Contains the ID used with the SetConfiguration request to specify that current configuration of the device connected to the indicated port. For an explanation of this value, see the Universal Serial Bus Specification.


### -field Speed

Contains a value of type <a href="..\usbspec\ne-usbspec-_usb_device_speed.md">USB_DEVICE_SPEED</a> that indicates the speed of the device. 


### -field DeviceIsHub

Indicates, when <b>TRUE</b>, that the device attached to the port is a hub.


### -field DeviceAddress

Contains the USB-assigned, bus-relative address of the device that is attached to the port.


### -field NumberOfOpenPipes

Indicates the number of open USB pipes associated with the port.


### -field ConnectionStatus

Contains an enumerator of type <a href="..\usbioctl\ne-usbioctl-_usb_connection_status.md">USB_CONNECTION_STATUS</a> that indicates the connection status.


### -field PipeList

Contains an array of structures of type <a href="..\usbioctl\ns-usbioctl-_usb_pipe_info.md">USB_PIPE_INFO</a> that describes the open pipes associated with the port. Pipe descriptions include the schedule offset of the pipe and the associated endpoint descriptor. This information can be used to calculate bandwidth usage.


## -remarks



If there is no device connected, <a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_node_connection_information_ex.md">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX</a> just returns information about the port. If a device is connected to the port <b>IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX</b> returns information about both the port and the connected device.

The <b>USB_NODE_CONNECTION_INFORMATION_EX</b> structure is an extended version of <a href="..\usbioctl\ns-usbioctl-_usb_node_connection_information.md">USB_NODE_CONNECTION_INFORMATION</a>. The two structures are identical, except for one member. In the extended structure, the <b>Speed</b> member indicates the device speed.  

The <b>Speed</b> member of the <b>USB_NODE_CONNECTION_INFORMATION_EX</b> structure is a UCHAR and it can specify any of the values of the <a href="..\usbspec\ne-usbspec-_usb_device_speed.md">USB_DEVICE_SPEED</a> enumerator.




## -see-also

<a href="..\usbioctl\ne-usbioctl-_usb_connection_status.md">USB_CONNECTION_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>



<a href="..\usbioctl\ns-usbioctl-_usb_pipe_info.md">USB_PIPE_INFO</a>



 

 


