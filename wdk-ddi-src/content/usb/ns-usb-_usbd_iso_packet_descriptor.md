---
UID: NS:usb._USBD_ISO_PACKET_DESCRIPTOR
title: _USBD_ISO_PACKET_DESCRIPTOR (usb.h)
description: The USBD_ISO_PACKET_DESCRIPTOR structure is used by USB client drivers to describe an isochronous transfer packet.
old-location: buses\usbd_iso_packet_descriptor.htm
tech.root: usbref
ms.assetid: 45ceff8e-a013-45de-be2e-42c6ca30147e
ms.date: 05/07/2018
keywords: ["_USBD_ISO_PACKET_DESCRIPTOR structure"]
ms.keywords: "*PUSBD_ISO_PACKET_DESCRIPTOR, PUSBD_ISO_PACKET_DESCRIPTOR, PUSBD_ISO_PACKET_DESCRIPTOR structure pointer [Buses], USBD_ISO_PACKET_DESCRIPTOR, USBD_ISO_PACKET_DESCRIPTOR structure [Buses], _USBD_ISO_PACKET_DESCRIPTOR, buses.usbd_iso_packet_descriptor, usb/PUSBD_ISO_PACKET_DESCRIPTOR, usb/USBD_ISO_PACKET_DESCRIPTOR, usbstrct_142becb1-b374-467e-9a11-2cda26e69ff4.xml"
f1_keywords:
 - "usb/USBD_ISO_PACKET_DESCRIPTOR"
 - "USBD_ISO_PACKET_DESCRIPTOR"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- usb.h
api_name:
- USBD_ISO_PACKET_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: USBD_ISO_PACKET_DESCRIPTOR, *PUSBD_ISO_PACKET_DESCRIPTOR
---

# _USBD_ISO_PACKET_DESCRIPTOR structure


## -description


The <b>USBD_ISO_PACKET_DESCRIPTOR</b>   structure is used by USB client drivers to describe an isochronous transfer packet.


## -struct-fields




### -field Offset

Specifies the offset, in bytes, of the buffer for this packet from the beginning of the entire isochronous transfer buffer.


### -field Length

 Set by the host controller to indicate the actual number of bytes received from the device for isochronous IN transfers. <b>Length</b> not used for isochronous OUT transfers.


### -field Status

Contains the status, on return from the host controller driver, of this transfer packet.


## -remarks



This structure is used as part of an isochronous transfer request to the host controller driver using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_isoch_transfer">_URB_ISOCH_TRANSFER</a> structure. The <b>Offset</b> member contains the offset from the beginning of the <b>TransferBuffer</b> or <b>TransferBufferMDL</b> members of  <b>_URB_ISOCH_TRANSFER</b>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">How to Transfer Data to USB Isochronous Endpoints</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">USB Structures</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbdlib/nf-usbdlib-usbd_isochurballocate">USBD_IsochUrbAllocate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb_isoch_transfer">_URB_ISOCH_TRANSFER</a>
 

 

