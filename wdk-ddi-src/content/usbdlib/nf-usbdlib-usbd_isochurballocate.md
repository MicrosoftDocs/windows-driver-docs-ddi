---
UID: NF:usbdlib.USBD_IsochUrbAllocate
title: USBD_IsochUrbAllocate function (usbdlib.h)
description: The USBD_IsochUrbAllocate routine allocates and formats a URB structure for an isochronous transfer request.
old-location: buses\usbd_isochurballocate.htm
tech.root: usbref
ms.date: 02/08/2022
keywords: ["USBD_IsochUrbAllocate function"]
ms.keywords: USBD_IsochUrbAllocate, USBD_IsochUrbAllocate routine [Buses], buses.usbd_isochurballocate, usbdlib/USBD_IsochUrbAllocate
req.header: usbdlib.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Requires WDK for Windows 8. Targets Windows Vista and later versions of the Windows operating system.
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
req.lib: Usbdex.lib
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - USBD_IsochUrbAllocate
 - usbdlib/USBD_IsochUrbAllocate
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Usbdex.lib
 - Usbdex.dll
api_name:
 - USBD_IsochUrbAllocate
---

# USBD_IsochUrbAllocate function

## -description

The **USBD_IsochUrbAllocate** routine allocates and formats a [URB](../usb/ns-usb-_urb.md) structure for an isochronous transfer request.

> [!NOTE]
> **For Windows Driver Framework (WDF) Drivers:** If your client driver is WDF-based, you must call the [WdfUsbTargetDeviceCreateIsochUrb](../wdfusb/nf-wdfusb-wdfusbtargetdevicecreateisochurb.md) method instead of **USBD_IsochUrbAllocate** to allocate memory for the [URB](../usb/ns-usb-_urb.md) structure.

## -parameters

### -param USBDHandle [in]

USBD handle that is retrieved by the client driver in a previous call to  the [USBD_CreateHandle](nf-usbdlib-usbd_createhandle.md) routine.

### -param NumberOfIsochPackets [in]

Specifies the maximum number of isochronous packets required to perform the transfer. The transfer buffer is described in a variable-length array of [USBD_ISO_PACKET_DESCRIPTOR](../usb/ns-usb-_usbd_iso_packet_descriptor.md) structures that stores information about each packet, such as byte offset of the packet within the buffer. The array is specified in the **IsoPacket** member of the [_URB_ISOCH_TRANSFER](../usb/ns-usb-_urb_isoch_transfer.md) structure, which is used to define the format of an isochronous request URB.

### -param Urb [out]

Pointer to an [URB](../usb/ns-usb-_urb.md) structure, which receives the URB allocated by **USBD_IsochUrbAllocate**. All members of the URB structure are set to zero. The allocated URB is large enough to hold the  maximum number of isochronous packets indicated by **NumberOfIsochPacket**.

The client driver must free the URB when the driver has finished using it by calling [USBD_UrbFree](nf-usbdlib-usbd_urbfree.md).

## -returns

The **USBD_IsochUrbAllocate** routine returns STATUS_SUCCESS if the request is successful. Otherwise, [USBD_UrbAllocate](nf-usbdlib-usbd_urballocate.md) sets *Urb* to `NULL` and returns an NT status failure code.

Possible values include, but are not limited to, STATUS_INVALID_PARAMETER, which indicates the caller passed in `NULL` to *USBDHandle* or *Urb*.

## -see-also

- [Allocating and Building URBs](/windows-hardware/drivers/usbcon/how-to-add-xrb-support-for-client-drivers)
- [How to Transfer Data to USB Isochronous Endpoints](../index.yml)
- [USBD_ISO_PACKET_DESCRIPTOR](../usb/ns-usb-_usbd_iso_packet_descriptor.md)
- [_URB_ISOCH_TRANSFER](../usb/ns-usb-_urb_isoch_transfer.md)