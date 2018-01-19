---
UID: NI:winsmcrd.IOCTL_SMARTCARD_TRANSMIT
title: IOCTL_SMARTCARD_TRANSMIT
author: windows-driver-content
description: Transmits data from the client to the detected smart card in ISO7816-4 compliant APDU.
old-location: nfpdrivers\ioctl_smartcard_transmit.htm
old-project: nfpdrivers
ms.assetid: FE6CB06D-C418-4B9E-B5F6-8579B1ED5974
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: GdiStartPageEMF
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: winsmcrd.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_SMARTCARD_TRANSMIT
req.alt-loc: winsmcrd.h
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
req.typenames: DOT11_WPS_DEVICE_NAME, *PDOT11_WPS_DEVICE_NAME
req.product: Windows 10 or later.
---

# IOCTL_SMARTCARD_TRANSMIT IOCTL



## -description
Transmits data from the client to the detected smart card in ISO7816-4 compliant APDU. These APDUs are interpreted with respect to the PC/SC specification (Section 4.3.7 has more detailed requirements on support for different NFC contactless tag formats). Because the NFP feature shares the same driver with the smartcard, the card should be connected right after the discovery, no explicit connect for the ‘Transmit’ is needed.



## -ioctlparameters

### -input-buffer
Bytes buffer contains a pointer to SCARD_IO_REQUEST structure followed by the data to be transmitted.


### -input-buffer-length

<text></text>

### -output-buffer
Bytes buffer contains the result of the transmission. The buffer points to the SCARD_IO_REQUEST structure immediately followed by the data received.


### -output-buffer-length

<text></text>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<b>Irp-&gt;IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful. Possible error codes are:

 


## -remarks


## -see-also
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a></dt>
<dt><a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/design-guide-smart-card">Smart card design guide</a></dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20IOCTL_SMARTCARD_TRANSMIT control code%20 RELEASE:%20(12/18/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

