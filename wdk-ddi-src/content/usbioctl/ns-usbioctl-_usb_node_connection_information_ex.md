---
UID: NS:usbioctl._USB_NODE_CONNECTION_INFORMATION_EX
title: _USB_NODE_CONNECTION_INFORMATION_EX (usbioctl.h)
description: The USB_NODE_CONNECTION_INFORMATION_EX structure is used in conjunction with the IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX request to obtain information about the connection associated with the indicated USB port.
old-location: buses\usb_node_connection_information_ex.htm
tech.root: usbref
ms.date: 12/15/2023
keywords: ["USB_NODE_CONNECTION_INFORMATION_EX structure"]
ms.keywords: "*PUSB_NODE_CONNECTION_INFORMATION_EX, PUSB_NODE_CONNECTION_INFORMATION_EX, PUSB_NODE_CONNECTION_INFORMATION_EX structure pointer [Buses], USB_NODE_CONNECTION_INFORMATION_EX, USB_NODE_CONNECTION_INFORMATION_EX structure [Buses], _USB_NODE_CONNECTION_INFORMATION_EX, buses.usb_node_connection_information_ex, usbioctl/PUSB_NODE_CONNECTION_INFORMATION_EX, usbioctl/USB_NODE_CONNECTION_INFORMATION_EX, usbstrct_2ee693b4-4279-4f3a-bbfb-1855f9b917d6.xml"
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
targetos: Windows
req.typenames: USB_NODE_CONNECTION_INFORMATION_EX, *PUSB_NODE_CONNECTION_INFORMATION_EX
f1_keywords:
 - _USB_NODE_CONNECTION_INFORMATION_EX
 - usbioctl/_USB_NODE_CONNECTION_INFORMATION_EX
 - PUSB_NODE_CONNECTION_INFORMATION_EX
 - usbioctl/PUSB_NODE_CONNECTION_INFORMATION_EX
 - USB_NODE_CONNECTION_INFORMATION_EX
 - usbioctl/USB_NODE_CONNECTION_INFORMATION_EX
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbioctl.h
api_name:
 - _USB_NODE_CONNECTION_INFORMATION_EX
 - PUSB_NODE_CONNECTION_INFORMATION_EX
 - USB_NODE_CONNECTION_INFORMATION_EX
---

# _USB_NODE_CONNECTION_INFORMATION_EX structure

## -description

The **USB_NODE_CONNECTION_INFORMATION_EX** structure is used in conjunction with the **[IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX](ni-usbioctl-ioctl_usb_get_node_connection_information_ex.md)** request to obtain information about the connection associated with the indicated USB port.

## -struct-fields

### -field ConnectionIndex

Contains a value greater than or equal to 1 that specifies the number of the port.

### -field DeviceDescriptor

Contains a structure of type **[USB_DEVICE_DESCRIPTOR](../usbspec/ns-usbspec-_usb_device_descriptor.md)** that reports the USB device descriptor returned by the attached device during enumeration.

### -field CurrentConfigurationValue

Contains the ID used with the SetConfiguration request to specify that current configuration of the device connected to the indicated port. For an explanation of this value, see section 9.4.7 in the Universal Serial Bus 3.1 Specification available at [USB Document Library](https://www.usb.org/documents).

### -field Speed

Contains a value of type **[USB_DEVICE_SPEED](../usbspec/ne-usbspec-_usb_device_speed.md)** that indicates the speed of the device.

### -field DeviceIsHub

Indicates, when **TRUE**, that the device attached to the port is a hub.

### -field DeviceAddress

Contains the USB-assigned, bus-relative address of the device that is attached to the port.

### -field NumberOfOpenPipes

Indicates the number of open USB pipes associated with the port.

### -field ConnectionStatus

Contains an enumerator of type **[USB_CONNECTION_STATUS](ne-usbioctl-_usb_connection_status.md)** that indicates the connection status.

### -field PipeList

Contains an array of structures of type **[USB_PIPE_INFO](ns-usbioctl-_usb_pipe_info.md)** that describes the open pipes associated with the port. Pipe descriptions include the schedule offset of the pipe and the associated endpoint descriptor. This information can be used to calculate bandwidth usage.

## -remarks

If there is no device connected, **[IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX](ni-usbioctl-ioctl_usb_get_node_connection_information_ex.md)**` just returns information about the port. If a device is connected to the port **IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX** returns information about both the port and the connected device.

The **USB_NODE_CONNECTION_INFORMATION_EX** structure is an extended version of **[USB_NODE_CONNECTION_INFORMATION](ns-usbioctl-_usb_node_connection_information.md)**. The two structures are identical, except for one member. In the extended structure, the **Speed** member indicates the device speed.

The **Speed** member of the **USB_NODE_CONNECTION_INFORMATION_EX** structure is a UCHAR and it can specify any of the values of the **[USB_DEVICE_SPEED](../usbspec/ne-usbspec-_usb_device_speed.md)** enumerator. The **Speed** member supports up to *UsbHighSpeed* (USB 2.0). To determine if a device supports *UsbSuperSpeed* (USB 3.0), use the **[USB_NODE_CONNECTION_INFORMATION_EX_V2](ns-usbioctl-_usb_node_connection_information_ex_v2.md)** structure.

The following C++ code snippet from the [USBView sample](https://github.com/microsoft/Windows-driver-samples/tree/main/usb/usbview) demonstrates how to determine if a device supports UsbSuperSpeed (USB 3.0):

```cpp
// Since the USB_NODE_CONNECTION_INFORMATION_EX is used to display
// the device speed, but the hub driver doesn't support indication
// of superspeed, we overwrite the value if the super speed
// data structures are available and indicate the device is operating
// at SuperSpeed.

if (connectionInfoEx->Speed == UsbHighSpeed 
    && connectionInfoExV2 != NULL 
    && (connectionInfoExV2->Flags.DeviceIsOperatingAtSuperSpeedOrHigher ||
        connectionInfoExV2->Flags.DeviceIsOperatingAtSuperSpeedPlusOrHigher))
{
    connectionInfoEx->Speed = UsbSuperSpeed;
}
```

## -see-also

- [USB Structures](../_usbref/index.md#structures)
- **[USB_CONNECTION_STATUS](ne-usbioctl-_usb_connection_status.md)**
- **[USB_PIPE_INFO](ns-usbioctl-_usb_pipe_info.md)**
- **[IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX](ni-usbioctl-ioctl_usb_get_node_connection_information_ex.md)**
- **[USB_NODE_CONNECTION_INFORMATION](ns-usbioctl-_usb_node_connection_information.md)**
- **[USB_DEVICE_SPEED](../usbspec/ne-usbspec-_usb_device_speed.md)**
- **[USB_NODE_CONNECTION_INFORMATION_EX_V2](ns-usbioctl-_usb_node_connection_information_ex_v2.md)**
- [USB samples](https://github.com/microsoft/Windows-driver-samples/tree/main/usb)
- [USBView sample](https://github.com/microsoft/Windows-driver-samples/tree/main/usb/usbview)
