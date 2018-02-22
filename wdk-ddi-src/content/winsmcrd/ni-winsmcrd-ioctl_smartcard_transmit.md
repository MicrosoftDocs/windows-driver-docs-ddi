---
UID: NI:winsmcrd.IOCTL_SMARTCARD_TRANSMIT
title: IOCTL_SMARTCARD_TRANSMIT
author: windows-driver-content
description: Transmits data from the client to the detected smart card in ISO7816-4 compliant APDU.
old-location: nfpdrivers\ioctl_smartcard_transmit.htm
old-project: nfpdrivers
ms.assetid: FE6CB06D-C418-4B9E-B5F6-8579B1ED5974
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: nfpdrivers.ioctl_smartcard_transmit, IOCTL_SMARTCARD_TRANSMIT control code [Near-Field Proximity Drivers], IOCTL_SMARTCARD_TRANSMIT, winsmcrd/IOCTL_SMARTCARD_TRANSMIT
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	winsmcrd.h
apiname:
-	IOCTL_SMARTCARD_TRANSMIT
product: Windows
targetos: Windows
req.typenames: DOT11_WPS_DEVICE_NAME, *PDOT11_WPS_DEVICE_NAME
req.product: Windows 10 or later.
---

# IOCTL_SMARTCARD_TRANSMIT IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

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

<b>Irp-&gt;IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful. Possible error codes are:

<table>
<tr>
<td>Return Code</td>
<td>Description</td>
</tr>
<tr>
<td>STATUS_NO_MEDIA</td>
<td>This code is returned if no smart card is detected.</td>
</tr>
<tr>
<td>STATUS_INVALID_PARAMETER</td>
<td>This code is returned the buffer does not contain the SCARD_IO_REQUEST structure, or is otherwise invalid.</td>
</tr>
<tr>
<td>STATUS_INVALID_DEVICE_STATE</td>
<td>This code is returned if the caller tries to send data with the protocol different from the previously selected protocol.</td>
</tr>
<tr>
<td>STATUS_BUFFER_TOO_SMALL</td>
<td>This code is returned if the output buffer is too small for the return data.</td>
</tr>
<tr>
<td>STATUS_IO_TIMEOUT</td>
<td>This code is returned if the operation takes too long.</td>
</tr>
<tr>
<td>STATUS_DEVICE_POWERED_OFF</td>
<td>This code is returned if the proximity radio control is off.</td>
</tr>
</table>
 


## -see-also

<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/design-guide-smart-card">Smart card design guide</a>



<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20IOCTL_SMARTCARD_TRANSMIT control code%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

