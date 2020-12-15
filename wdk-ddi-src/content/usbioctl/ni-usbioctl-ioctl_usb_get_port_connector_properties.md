---
UID: NI:usbioctl.IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES
title: IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES (usbioctl.h)
description: The IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES I/O control request is sent by an application to retrieve information about a specific port on a USB hub.
old-location: buses\ioctl_usb_get_port_connector_properties.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES IOCTL"]
ms.keywords: IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES, IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES control, IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES control code [Buses], buses.ioctl_usb_get_port_connector_properties, usbioctl/IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES
 - usbioctl/IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Usbioctl.h
api_name:
 - IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES
---

# IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES IOCTL


## -description

The <b>IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES</b> I/O control request is sent by an application to retrieve information about a specific port on a USB hub. 

<b>IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES</b> is a user-mode I/O control request. This request targets the Universal Serial Bus (USB) hub device (GUID_DEVINTERFACE_USB_HUB).

## -ioctlparameters

### -input-buffer

<b>AssociatedIrp.SystemBuffer</b> points to a caller-allocated    <a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_port_connector_properties">USB_PORT_CONNECTOR_PROPERTIES</a> structure. The caller must set the structure members as follows:<ul>
<li>
The caller must specify the port number of the port being queried in the <b>ConnectionIndex</b> member.  <b>ConnectionIndex</b> must be a value in the range of 1 to <i>n</i>, where <i>n</i> is the highest port number retrieved in a previous <a href="/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_hub_information_ex">IOCTL_USB_GET_HUB_INFORMATION_EX</a> I/O control request.

</li>
<li>
The caller must specify the <b>CompanionIndex</b>  member. For a SuperSpeed hub, the caller must set the <b>CompanionIndex</b>  member to 0. 

The caller can use <b>CompanionIndex</b> to get port numbers associated with the port being queried. If more than one companion port is associated with the port, to get all port numbers, the application can send the request in a loop. Start with <b>CompanionIndex</b>  set to 0 and  increment the <b>CompanionIndex</b> value in each iteration until the request completes with <b>CompanionPortNumber</b> set to 0 and <b>CompanionHubSymbolicLinkName</b> is NULL. 

</li>
</ul>

### -input-buffer-length

The <b>Parameters.DeviceIoControl.InputBufferLength</b> member indicates the size, in bytes, of the caller-allocated buffer pointed to by <b>AssociatedIrp.SystemBuffer</b>. For more information see Remarks.

### -output-buffer

On output, <a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_port_connector_properties">USB_PORT_CONNECTOR_PROPERTIES</a>, pointed to by  <b>AssociatedIrp.SystemBuffer</b>,  is filled with information about the physical connector associated with the port.

### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member indicates the size, in bytes, of the output buffer <b>SystemBuffer</b>.

### -in-out-buffer

### -inout-buffer-length

### -status-block

The USB stack sets <b>Irp->IoStatus.Status</b> to STATUS_SUCCESS if the request is successful. Otherwise, the USB stack sets <b>Status</b> to the appropriate error condition, such as STATUS_INVALID_PARAMETER or STATUS_INSUFFICIENT_RESOURCES. If the hub has not been started or is not functional, the request returns STATUS_UNSUCCESSFUL.

## -remarks

The caller must supply a buffer that is large enough to hold a <a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_port_connector_properties">USB_PORT_CONNECTOR_PROPERTIES</a> structure and  the symbolic link name of a companion hub, if such a hub is associated with the specified port. To obtain the size of the buffer to allocate, the caller must send a <b>IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES</b> request. In the request, <b>AssociatedIrp.SystemBuffer</b> must be a caller-allocated <b>USB_PORT_CONNECTOR_PROPERTIES</b> structure and <b>Parameters.DeviceIoControl.InputBufferLength</b> must be  <code>sizeof(USB_PORT_CONNECTOR_PROPERTIES)</code>. Upon successful completion, the <b>ActualLength</b> member of <b>USB_PORT_CONNECTOR_PROPERTIES</b> indicates the actual size of the  buffer. If a symbolic link name exists, the received value includes the size of the string that stores the link name. 

Based on the <b>ActualLength</b> value, the caller can then allocate a buffer and send the  <b>IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES</b> request again. After the request completes, the buffer is filled with port information and the <b>CompanionHubSymbolicLinkName</b> member is a Unicode string that contains the symbolic link  name of the companion hub.

## -see-also

<a href="/windows-hardware/drivers/ddi/usbioctl/ni-usbioctl-ioctl_usb_get_port_connector_properties">IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES</a>



<a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_hub_information_ex">USB_HUB_INFORMATION_EX</a>



<a href="/windows-hardware/drivers/ddi/usbioctl/ns-usbioctl-_usb_port_connector_properties">USB_PORT_CONNECTOR_PROPERTIES</a>
