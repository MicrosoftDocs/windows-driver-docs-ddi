---
UID: NI:winsmcrd.IOCTL_SMARTCARD_GET_STATE
title: IOCTL_SMARTCARD_GET_STATE
author: windows-driver-content
description: The IOCTL_SMARTCARD_GET_STATE control code gets the current status of the smart card.
old-location: nfpdrivers\ioctl_smartcard_get_state.htm
old-project: nfpdrivers
ms.assetid: 18666E48-9505-448E-ABA1-536D365FC49D
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_SMARTCARD_GET_STATE, IOCTL_SMARTCARD_GET_STATE control code [Near-Field Proximity Drivers], nfpdrivers.ioctl_smartcard_get_state, winsmcrd/IOCTL_SMARTCARD_GET_STATE
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	winsmcrd.h
api_name:
-	IOCTL_SMARTCARD_GET_STATE
product: Windows
targetos: Windows
req.typenames: PRINTER_EVENT_ATTRIBUTES_INFO, *PPRINTER_EVENT_ATTRIBUTES_INFO
req.product: Windows 10 or later.
---

# IOCTL_SMARTCARD_GET_STATE IOCTL


## -description


The <b>IOCTL_SMARTCARD_GET_STATE</b> 
   control code  gets the current status of the smart card.


## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length



<text></text>




### -output-buffer

(DWORD) one of the following states:

<table>
<tr>
<th>State</th>
<th>Description</th>
</tr>
<tr>
<td>SCARD_UNKNOWN</td>
<td>Unknown state</td>
</tr>
<tr>
<td>SCARD_ABSENT</td>
<td>Card is not detected</td>
</tr>
<tr>
<td>SCARD_SWALLOWED</td>
<td>Card is present but not powered. When SCARD_POWER_DOWN is set.</td>
</tr>
<tr>
<td>SCARD_SPECIFIC</td>
<td>Card  is present and communication protocols are established.</td>
</tr>
</table>
 


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
<th>Return Code</th>
<th>Description</th>
</tr>
<tr>
<td>STATUS_INVALID_PARAMETER</td>
<td>This code is returned when the input or output buffers are invalid.</td>
</tr>
<tr>
<td>STATUS_BUFFER_TOO_SMALL</td>
<td>This code is returned if the output buffer is too small for the return data.</td>
</tr>
<tr>
<td>STATUS_DEVICE_POWERED_OFF</td>
<td>This code is returned if the proximity radio control is off.</td>
</tr>
</table>
 


## -see-also




<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>



<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/design-guide-smart-card">Smart card design guide</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20IOCTL_SMARTCARD_GET_STATE control code%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

