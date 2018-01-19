---
UID: NS:usb._USBD_ISO_PACKET_DESCRIPTOR
title: _USBD_ISO_PACKET_DESCRIPTOR
author: windows-driver-content
description: The USBD_ISO_PACKET_DESCRIPTOR structure is used by USB client drivers to describe an isochronous transfer packet.
old-location: buses\usbd_iso_packet_descriptor.htm
old-project: usbref
ms.assetid: 45ceff8e-a013-45de-be2e-42c6ca30147e
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _USBD_ISO_PACKET_DESCRIPTOR, USBD_ISO_PACKET_DESCRIPTOR, *PUSBD_ISO_PACKET_DESCRIPTOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usb.h
req.include-header: Usb.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: USBD_ISO_PACKET_DESCRIPTOR
req.alt-loc: usb.h
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
req.typenames: USBD_ISO_PACKET_DESCRIPTOR, *PUSBD_ISO_PACKET_DESCRIPTOR
req.product: Windows 10 or later.
---

# _USBD_ISO_PACKET_DESCRIPTOR structure



## -description
The <b>USBD_ISO_PACKET_DESCRIPTOR</b>   structure is used by USB client drivers to describe an isochronous transfer packet.



## -syntax

````
typedef struct _USBD_ISO_PACKET_DESCRIPTOR {
  ULONG       Offset;
  ULONG       Length;
  USBD_STATUS Status;
} USBD_ISO_PACKET_DESCRIPTOR, *PUSBD_ISO_PACKET_DESCRIPTOR;
````


## -struct-fields

### -field Offset

Specifies the offset, in bytes, of the buffer for this packet from the beginning of the entire isochronous transfer buffer.


### -field Length

 Set by the host controller to indicate the actual number of bytes received from the device for isochronous IN transfers. <b>Length</b> not used for isochronous OUT transfers.


### -field Status

Contains the status, on return from the host controller driver, of this transfer packet.


## -remarks
This structure is used as part of an isochronous transfer request to the host controller driver using the <a href="..\usb\ns-usb-_urb_isoch_transfer.md">_URB_ISOCH_TRANSFER</a> structure. The <b>Offset</b> member contains the offset from the beginning of the <b>TransferBuffer</b> or <b>TransferBufferMDL</b> members of  <b>_URB_ISOCH_TRANSFER</b>.


## -see-also
<dl>
<dt>
<a href="..\usbdlib\nf-usbdlib-usbd_isochurballocate.md">USBD_IsochUrbAllocate</a>
</dt>
<dt>
<a href="..\usb\ns-usb-_urb_isoch_transfer.md">_URB_ISOCH_TRANSFER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh406225">How to Transfer Data to USB Isochronous Endpoints</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540160">USB Structures</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBD_ISO_PACKET_DESCRIPTOR structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

