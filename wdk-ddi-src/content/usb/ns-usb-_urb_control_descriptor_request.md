---
UID: NS:usb._URB_CONTROL_DESCRIPTOR_REQUEST
title: _URB_CONTROL_DESCRIPTOR_REQUEST (usb.h)
description: The _URB_CONTROL_DESCRIPTOR_REQUEST structure is used by USB client drivers to get or set descriptors on a USB device.
old-location: buses\_urb_control_descriptor_request.htm
tech.root: usbref
ms.assetid: 770659f4-701f-47dc-b20f-e51c85cdee4b
ms.date: 05/07/2018
keywords: ["URB_CONTROL_DESCRIPTOR_REQUEST structure"]
ms.keywords: "_URB_CONTROL_DESCRIPTOR_REQUEST, _URB_CONTROL_DESCRIPTOR_REQUEST structure [Buses], buses._urb_control_descriptor_request, usb/_URB_CONTROL_DESCRIPTOR_REQUEST, usbstrct_f28020e9-3fa4-466c-8cc5-5630d3b06d9c.xml"
req.header: usb.h
req.include-header: Usb.h
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
req.typenames: 
f1_keywords:
 - _URB_CONTROL_DESCRIPTOR_REQUEST
 - usb/_URB_CONTROL_DESCRIPTOR_REQUEST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - usb.h
api_name:
 - _URB_CONTROL_DESCRIPTOR_REQUEST
---

# _URB_CONTROL_DESCRIPTOR_REQUEST structure


## -description

The <b>_URB_CONTROL_DESCRIPTOR_REQUEST</b> structure is used by USB client drivers to get or set descriptors on a USB device.

## -struct-fields

### -field Hdr

Pointer to a <a href="/windows-hardware/drivers/ddi/usb/ns-usb-_urb_header">_URB_HEADER</a> structure that specifies the URB header information. <b>Hdr.Function</b> must be one of the following:

<b>Hdr.Length</b> must equal <code>sizeof(_URB_CONTROL_DESCRIPTOR_REQUEST)</code>.

### -field Reserved

Reserved. Do not use.

### -field Reserved0

Reserved. Do not use.

### -field TransferBufferLength

Specifies the length, in bytes, of the buffer specified in <b>TransferBuffer</b> or described in <b>TransferBufferMDL</b>. The host controller driver returns the number of bytes sent to or read from the pipe in this member.

### -field TransferBuffer

Pointer to a resident buffer for the transfer or is <b>NULL</b> if an MDL is supplied in <b>TransferBufferMDL</b>.

### -field TransferBufferMDL

Pointer to an MDL that describes a resident buffer or is <b>NULL</b> if a buffer is supplied in <b>TransferBuffer</b>. This MDL must be allocated from nonpaged pool.

### -field UrbLink

Reserved. Do not use.

### -field hca

Reserved. Do not use.

### -field Reserved1

Reserved. Do not use.

### -field Index

Specifies the device-defined index of the descriptor that is being retrieved or set.

### -field DescriptorType

Indicates what type of descriptor is being retrieved or set. One of the following values must be specified:

| usbspec.h constant                                                | Value |     USB Version    |
|-------------------------------------------------------------------|:-----:|:------------------:|
| USB\_DEVICE\_DESCRIPTOR\_TYPE                                     |  0x01 |       USB 1.1      |
| USB\_CONFIGURATION\_DESCRIPTOR\_TYPE                              |  0x02 |       USB 1.1      |
| USB\_STRING\_DESCRIPTOR\_TYPE                                     |  0x03 |       USB 1.1      |
| USB\_INTERFACE\_DESCRIPTOR\_TYPE                                  |  0x04 |       USB 1.1      |
| USB\_ENDPOINT\_DESCRIPTOR\_TYPE                                   |  0x05 |       USB 1.1      |
| USB\_DEVICE\_QUALIFIER\_DESCRIPTOR\_TYPE                          |  0x06 |       USB 2.0      |
| USB\_OTHER\_SPEED\_CONFIGURATION\_DESCRIPTOR\_TYPE                |  0x07 |       USB 2.0      |
| USB\_INTERFACE\_POWER\_DESCRIPTOR\_TYPE                           |  0x08 |       USB 2.0      |
| USB\_OTG\_DESCRIPTOR\_TYPE                                        |  0x09 |       USB 3.0      |
| USB\_DEBUG\_DESCRIPTOR\_TYPE                                      |  0x0a |       USB 3.0      |
| USB\_INTERFACE\_ASSOCIATION\_DESCRIPTOR\_TYPE                     |  0x0b |       USB 3.0      |
| USB\_BOS\_DESCRIPTOR\_TYPE                                        |  0x0f |       USB 3.0      |
| USB\_DEVICE\_CAPABILITY\_DESCRIPTOR\_TYPE                         |  0x10 |       USB 3.0      |
| USB\_SUPERSPEED\_ENDPOINT\_COMPANION\_DESCRIPTOR\_TYPE            |  0x30 |       USB 3.0      |
| USB\_20\_HUB\_DESCRIPTOR\_TYPE                                    |  0x29 | USB 1.1<br>USB 2.0 |
| USB\_30\_HUB\_DESCRIPTOR\_TYPE                                    |  0x2a |       USB 3.0      |
| USB\_SUPERSPEEDPLUS\_ISOCH\_ENDPOINT\_COMPANION\_DESCRIPTOR\_TYPE |  0x31 |       USB 3.1      |

### -field LanguageId

Specifies the language ID of the descriptor to be retrieved when USB_STRING_DESCRIPTOR_TYPE is set in <b>DescriptorType</b>. This member must be set to zero for any other value in <b>DescriptorType</b>.

### -field Reserved2

Reserved. Do not use.

## -remarks

Drivers can use the <b>UsbBuildGetDescriptorRequest</b> service routine to format this URB. If the caller passes a buffer too small to hold all of the data, the bus driver truncates the data to fit in the buffer without error.

When the caller requests the device descriptor, the bus driver returns a <a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_device_descriptor">USB_DEVICE_DESCRIPTOR</a> data structure.

When the caller requests a configuration descriptor, the bus driver returns the configuration descriptor in a <a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_configuration_descriptor">USB_CONFIGURATION_DESCRIPTOR</a> structure, followed by the interface and endpoint descriptors for that configuration. The driver can access the interface and endpoint descriptors as <a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_interface_descriptor">USB_INTERFACE_DESCRIPTOR</a> and <a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_endpoint_descriptor">USB_ENDPOINT_DESCRIPTOR</a> structures. The bus driver also returns any class-specific or device-specific descriptors. The system provides the <a href="/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_parseconfigurationdescriptorex">USBD_ParseConfigurationDescriptorEx</a> and <a href="/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_parsedescriptors">USBD_ParseDescriptors</a> service routines to find individual descriptors within the buffer.

When the caller requests a string descriptor, the bus driver returns a <a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_string_descriptor">USB_STRING_DESCRIPTOR</a> structure. The string itself is found in the variable-length <b>bString</b> member of the string descriptor.

The reserved members of this structure must be treated as opaque and are reserved for system use.

## -see-also

<a href="/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a>



<a href="/windows-hardware/drivers/ddi/index">USB Structures</a>



<a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_configuration_descriptor">USB_CONFIGURATION_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_device_descriptor">USB_DEVICE_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_endpoint_descriptor">USB_ENDPOINT_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_interface_descriptor">USB_INTERFACE_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_string_descriptor">USB_STRING_DESCRIPTOR</a>



<a href="/windows-hardware/drivers/ddi/usb/ns-usb-_urb_header">_URB_HEADER</a>
