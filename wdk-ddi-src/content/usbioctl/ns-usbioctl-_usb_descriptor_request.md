---
UID: NS:usbioctl._USB_DESCRIPTOR_REQUEST
title: _USB_DESCRIPTOR_REQUEST (usbioctl.h)
description: The USB_DESCRIPTOR_REQUEST structure is used with the IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION I/O control request to retrieve one or more descriptors for the device that is associated with the indicated connection index.
old-location: buses\usb_descriptor_request.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["USB_DESCRIPTOR_REQUEST structure"]
ms.keywords: "*PUSB_DESCRIPTOR_REQUEST, PUSB_DESCRIPTOR_REQUEST, PUSB_DESCRIPTOR_REQUEST structure pointer [Buses], USB_DESCRIPTOR_REQUEST, USB_DESCRIPTOR_REQUEST structure [Buses], _USB_DESCRIPTOR_REQUEST, buses.usb_descriptor_request, usbioctl/PUSB_DESCRIPTOR_REQUEST, usbioctl/USB_DESCRIPTOR_REQUEST, usbstrct_b5a96c38-53d8-4d08-849b-d6c8c4b69c72.xml"
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
req.typenames: USB_DESCRIPTOR_REQUEST, *PUSB_DESCRIPTOR_REQUEST
f1_keywords:
 - _USB_DESCRIPTOR_REQUEST
 - usbioctl/_USB_DESCRIPTOR_REQUEST
 - PUSB_DESCRIPTOR_REQUEST
 - usbioctl/PUSB_DESCRIPTOR_REQUEST
 - USB_DESCRIPTOR_REQUEST
 - usbioctl/USB_DESCRIPTOR_REQUEST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usbioctl.h
api_name:
 - _USB_DESCRIPTOR_REQUEST
 - PUSB_DESCRIPTOR_REQUEST
 - USB_DESCRIPTOR_REQUEST
---

# _USB_DESCRIPTOR_REQUEST structure


## -description

The <b>USB_DESCRIPTOR_REQUEST</b> structure is used with the <a href="/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_descriptor_from_node_connection">IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION</a> I/O control request to retrieve one or more descriptors for the device that is associated with the indicated connection index. The fields in this structure are described in the Universal Serial Bus 3.1 Specification available at [USB Document Library](https://www.usb.org/documents).

## -struct-fields

### -field ConnectionIndex

The port whose descriptors are retrieved.

### -field SetupPacket

The members of the <b>SetupPacket</b> structure defined as per the official specification. See section 9.3.

### -field SetupPacket.bmRequest

The type of USB device request (standard, class, or vendor), the direction of the data transfer, and the type of data recipient (device, interface, or endpoint). On input to the <a href="/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_descriptor_from_node_connection">IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION</a> I/O control request, the USB stack ignores the value of <b>bmRequest</b> and inserts a value of 0x80. This value indicates a standard USB device request and a device-to-host data transfer.

### -field SetupPacket.bRequest

The request number. On input to the <a href="/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_descriptor_from_node_connection">IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION</a> I/O control request, the USB stack ignores the value of <b>bRequest</b> and inserts a value of 0x06. This value indicates a request of <b>GET_DESCRIPTOR</b>.

### -field SetupPacket.wValue

On input to the <a href="/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_descriptor_from_node_connection">IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION</a> I/O control request, the caller should specify the type of descriptor to retrieve in the high byte of <b>wValue</b> and the descriptor index in the low byte. The following table lists the possible descriptor types. These constant types are defined in the Usbspec.h header included in the Windows Driver Kit.

<table>
<tr>
<th>Descriptor type</th>
<th>Meaning</th>
</tr>
<tr>
<td>
USB_DEVICE_DESCRIPTOR_TYPE

</td>
<td>
Instructs the USB stack to return the device descriptor.

</td>
</tr>
<tr>
<td>
USB_CONFIGURATION_DESCRIPTOR_TYPE

</td>
<td>
Instructs the USB stack to return the configuration descriptor and all interface, endpoint, class-specific, and vendor-specific descriptors associated with the current configuration.

</td>
</tr>
<tr>
<td>
USB_STRING_DESCRIPTOR_TYPE

</td>
<td>
Instructs the USB stack to return the indicated string descriptor.

</td>
</tr>
<tr>
<td>
USB_INTERFACE_DESCRIPTOR_TYPE

</td>
<td>
Instructs the USB stack to return the indicated interface descriptor.

</td>
</tr>
<tr>
<td>
USB_ENDPOINT_DESCRIPTOR_TYPE

</td>
<td>
Instructs the USB stack to return the indicated endpoint descriptor.

</td>
</tr>
</table>

### -field SetupPacket.wIndex

The device-specific index of the descriptor that is to be retrieved.

### -field SetupPacket.wLength

The length of the data that is transferred during the second phase of the control transfer.

### -field Data

On output from the <a href="/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_descriptor_from_node_connection">IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION</a> I/O control request, this member contains the retrieved descriptors.

## -remarks

If the caller specifies a value of USB_CONFIGURATION_DESCRIPTOR_TYPE in the <b>wValue</b> member, the output buffer must be large enough to hold all of the descriptors that are associated with the current configuration, or the request will fail.

## -see-also

<a href="/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_descriptor_from_node_connection">IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION</a>



<a href="/windows-hardware/drivers/ddi/_usbref/#structures">USB Structures</a>

