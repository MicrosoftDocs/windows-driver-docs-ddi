---
UID: NI:winsmcrd.IOCTL_SMARTCARD_GET_ATTRIBUTE
title: IOCTL_SMARTCARD_GET_ATTRIBUTE (winsmcrd.h)
description: The IOCTL_SMARTCARD_GET_ATTRIBUTE control code queries for smart card attribues.
old-location: nfpdrivers\ioctl_smartcard_get_attribute.htm
tech.root: nfpdrivers
ms.assetid: 5B5F4CA1-0E49-4D60-AD78-3294C80844E1
ms.date: 02/15/2018
ms.keywords: IOCTL_SMARTCARD_GET_ATTRIBUTE, IOCTL_SMARTCARD_GET_ATTRIBUTE control, IOCTL_SMARTCARD_GET_ATTRIBUTE control code [Near-Field Proximity Drivers], nfpdrivers.ioctl_smartcard_get_attribute, winsmcrd/IOCTL_SMARTCARD_GET_ATTRIBUTE
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- winsmcrd.h
api_name:
- IOCTL_SMARTCARD_GET_ATTRIBUTE
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SMARTCARD_GET_ATTRIBUTE IOCTL


## -description


The <b>IOCTL_SMARTCARD_GET_ATTRIBUTE</b> 
   control code queries for smart card attribues. 


## -ioctlparameters




### -input-buffer

(DWORD) contains the attribute tag.


### -input-buffer-length








### -output-buffer

(DWORD) contains the attribute tag.


### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp-&gt;IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful. Possible error codes are:

<table>
<tr>
<th>Return Code</th>
<th>Description</th>
</tr>
<tr>
<td>STATUS_NOT_SUPPORTED</td>
<td>This code is returned if the attribute is not supported.</td>
</tr>
<tr>
<td>STATUS_INVALID_PARAMETER</td>
<td>This code is returned if the input or output buffers are invalid.</td>
</tr>
<tr>
<td>STATUS_BUFFER_TOO_SMALL</td>
<td>This code is returned if the output buffer is too small for the return data.</td>
</tr>
<tr>
<td>STATUS_INVALID_DEVICE_STATE</td>
<td>This code is returned if the device cannot accept the request.</td>
</tr>
<tr>
<td>STATUS_DEVICE_POWERED_OFF</td>
<td>This code is returned if the proximity radio control is off when the call is made.</td>
</tr>
</table>
 


## -remarks



The following actions are required when using this IOCTL:<ul>
<li>

The driver must support CancelIo on this pended IOCTL.

</li>
<li>If this IOCTL is issued when the NFCC is in RF discovery state, the driver needs to put the NFCC into RF idle state, configure the routing table, and restart RF discovery.</li>
</ul>





## -see-also




<a href="https://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>



<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/design-guide-smart-card">Smart card design guide</a>
 

 

