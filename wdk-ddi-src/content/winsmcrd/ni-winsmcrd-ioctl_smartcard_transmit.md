---
UID: NI:winsmcrd.IOCTL_SMARTCARD_TRANSMIT
title: IOCTL_SMARTCARD_TRANSMIT (winsmcrd.h)
description: Transmits data from the client to the detected smart card in ISO7816-4 compliant APDU.
old-location: nfpdrivers\ioctl_smartcard_transmit.htm
tech.root: nfpdrivers
ms.date: 07/15/2022
keywords: ["IOCTL_SMARTCARD_TRANSMIT IOCTL"]
ms.keywords: IOCTL_SMARTCARD_TRANSMIT, IOCTL_SMARTCARD_TRANSMIT control, IOCTL_SMARTCARD_TRANSMIT control code [Near-Field Proximity Drivers], nfpdrivers.ioctl_smartcard_transmit, winsmcrd/IOCTL_SMARTCARD_TRANSMIT
req.header: winsmcrd.h
req.include-header: 
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
 - IOCTL_SMARTCARD_TRANSMIT
 - winsmcrd/IOCTL_SMARTCARD_TRANSMIT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winsmcrd.h
api_name:
 - IOCTL_SMARTCARD_TRANSMIT
---

# IOCTL_SMARTCARD_TRANSMIT IOCTL

## -description

The **IOCTL_SMARTCARD_TRANSMIT** request transmits data to, and receives data from, the inserted smart card.

## -ioctlparameters

### -input-buffer

* **Irp->AssociatedIrp.SystemBuffer**
  A pointer to an [**SCARD_IO_REQUEST**](ns-winsmcrd-_scard_io_request.md) structure followed by the data to transmit to the inserted smart card.

### -input-buffer-length

* **Parameters.DeviceIoControl.InputBufferLength**
  Contains the size of the structure plus the length of trailing data bytes (if any). The **dwProtocol** member must be set to the protocol that was previously selected, and the **cbPciLength** member must be set to the size of the **SCARD_IO_REQUEST** structure itself (usually eight bytes). The structure is used for future protocols. Data that will be transmitted to the card must immediately follow this structure.

### -output-buffer

Bytes buffer contains the result of the transmission. The buffer points to the SCARD_IO_REQUEST structure immediately followed by the data received.

* **Irp->AssociatedIrp.SystemBuffer**
  Receives the result of the transmission. This buffer must also begin with an [**SCARD_IO_REQUEST**](ns-winsmcrd-_scard_io_request.md) structure. Any data that was received from the card must be stored immediately after the structure.

### -output-buffer-length

* **Parameters.DeviceIoControl.OutputBufferLength**
  Contains the length of the output buffer.

### -in-out-buffer

### -inout-buffer-length

### -status-block

**Irp->IoStatus.Status** is set to one of the following values.

| Value | Meaning |
| ----- | ------- |
| STATUS_SUCCESS              | The transmission was successful. |
| STATUS_NO_MEDIA             | No smart card is detected in the reader. |
| STATUS_IO_TIMEOUT           | The operation timed out. |
| STATUS_INVALID_DEVICE_STATE | The protocol in the header file does not match the smart card protocol that was previously selected. |
| STATUS_BUFFER_TOO_SMALL     | The output buffer is too small for the return data. |
| STATUS_DEVICE_POWERED_OFF   | The proximity radio control is off. |

## -remarks

**IOCTL_SMARTCARD_TRANSMIT** transmits data from the client to the detected smart card in ISO7816-4 compliant APDU. These APDUs are interpreted with respect to the PC/SC specification (Section 4.3.7 has more detailed requirements on support for different NFC contactless tag formats). Because the NFP feature shares the same driver with the smart card, the card should be connected right after the discovery, no explicit connect for the ‘Transmit’ is needed.

Because the input buffer and the output buffer are pointing to the same memory area, the driver must avoid overwriting the input data. Use the smart card driver library to make sure that the input data is not overwritten.

## -see-also

[Near field communication (NFC) design guide](/windows-hardware/drivers/nfc/)

[Smart card design guide](/windows-hardware/drivers/nfc/design-guide-smart-card)
