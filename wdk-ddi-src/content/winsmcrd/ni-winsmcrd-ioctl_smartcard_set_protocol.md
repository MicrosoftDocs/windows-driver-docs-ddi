---
UID: NI:winsmcrd.IOCTL_SMARTCARD_SET_PROTOCOL
title: IOCTL_SMARTCARD_SET_PROTOCOL (winsmcrd.h)
description: Sets the procotol the driver communicates to the smart card with after the card is detected.
old-location: nfpdrivers\ioctl_smartcard_set_protocol.htm
tech.root: nfpdrivers
ms.assetid: 9A54D427-128F-41C1-B6BD-EE09B0402C32
ms.date: 02/15/2018
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

Sets the procotol the driver communicates to the smart card with after the card is detected.

## -ioctlparameters

### -input-buffer

(DWORD) mask of protocols below:<ul>
<li>SCARD_PROTOCOL_T1</li>
<li>SCARD_PROTOCOL_DEFAULT</li>
<li>SCARD_PROTOCOL_OPTIMAL</li>
</ul>

### -input-buffer-length

### -output-buffer

(DWORD) contains the selected protocol (for example, SCARD_PROTOCOL_T1).

### -output-buffer-length

### -in-out-buffer

### -inout-buffer-length

### -status-block

Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.

Otherwise, Status to the appropriate error condition as a NTSTATUS code. 

For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).

## -see-also

<a href="https://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/nfc/design-guide-smart-card">Smart card design guide</a>

