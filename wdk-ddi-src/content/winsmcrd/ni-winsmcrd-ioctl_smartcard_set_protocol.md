---
UID: NI:winsmcrd.IOCTL_SMARTCARD_SET_PROTOCOL
title: IOCTL_SMARTCARD_SET_PROTOCOL (winsmcrd.h)
description: Sets the procotol the driver communicates to the smart card with after the card is detected.
old-location: nfpdrivers\ioctl_smartcard_set_protocol.htm
tech.root: nfpdrivers
ms.date: 07/15/2022
keywords: ["IOCTL_SMARTCARD_SET_PROTOCOL IOCTL"]
ms.keywords: IOCTL_SMARTCARD_SET_PROTOCOL, IOCTL_SMARTCARD_SET_PROTOCOL control, IOCTL_SMARTCARD_SET_PROTOCOL control code [Near-Field Proximity Drivers], nfpdrivers.ioctl_smartcard_set_protocol, winsmcrd/IOCTL_SMARTCARD_SET_PROTOCOL
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
 - IOCTL_SMARTCARD_SET_PROTOCOL
 - winsmcrd/IOCTL_SMARTCARD_SET_PROTOCOL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - winsmcrd.h
api_name:
 - IOCTL_SMARTCARD_SET_PROTOCOL
---

# IOCTL_SMARTCARD_SET_PROTOCOL IOCTL

## -description

The **IOCTL_SMARTCARD_SET_PROTOCOL** request sets the protocol that the driver will use to communicate with the smart card after the card is detected (inserted).

## -ioctlparameters

### -input-buffer

* **Irp->AssociatedIrp.SystemBuffer**
  Contains a mask of protocols that are acceptable for the following transmissions. The mask can be a bitwise OR of the following values:

  * SCARD_PROTOCOL_RAW
  * SCARD_PROTOCOL_T0
  * SCARD_PROTOCOL_T1
  * SCARD_PROTOCOL_DEFAULT
  * SCARD_PROTOCOL_OPTIMAL

  The last two values are additional bit definitions that indicate that the driver must either explicitly perform protocol type selection (PTS) with the best possible communication parameters (SCARD_PROTOCOL_OPTIMAL) or use the implicit protocol of the card with standard parameters (SCARD_PROTOCOL_DEFAULT). If the card supports only one protocol with one set of communication parameters, the bits are ignored.

* **Parameters.DeviceIoControl.InputBufferLength**
  Must be set to sizeof(ULONG). The driver decides which protocol out of the mask to use with the inserted card.

### -input-buffer-length

### -output-buffer

* **Irp->AssociatedIrp.SystemBuffer**
  The driver stores the selected protocol here (for example, SCARD_PROTOCOL_T1). Only one bit out of the mask can be set.

### -output-buffer-length

* **Parameters.DeviceIoControl.OutputBufferLength**
  Must be sizeof(ULONG).

### -in-out-buffer

### -inout-buffer-length

### -status-block

**Irp->IoStatus.Information** must be set to sizeof(ULONG).

**Irp->IoStatus.Status** is set to one of the following values.

| Value | Meaning |
| ----- | ------- |
| STATUS_SUCCESS                | A protocol was successfully selected. |
| STATUS_NO_MEDIA               | No smart card is detected in the reader. |
| STATUS_IO_TIMEOUT             | The operation timed out. |
| STATUS_NOT_SUPPORTED          | The smart card does not support any of the requested protocols. |
| STATUS_INVALID_DEVICE_REQUEST | The mask contains no known protocol. |

For more information, see [NTSTATUS Values](/windows-hardware/drivers/kernel/ntstatus-values).

## -see-also

[Near field communication (NFC) design guide](/windows-hardware/drivers/nfc/)

[Smart card design guide](/windows-hardware/drivers/nfc/design-guide-smart-card)
