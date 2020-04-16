---
UID: NI:winsmcrd.IOCTL_SMARTCARD_IS_ABSENT
title: IOCTL_SMARTCARD_IS_ABSENT (winsmcrd.h)
description: The IOCTL_SMARTCARD_IS_ABSENT control code returns immediately with STATUS_SUCCESS if no smart card is currently detected.
old-location: nfpdrivers\ioctl_smartcard_is_absent.htm
tech.root: nfpdrivers
ms.assetid: A9E4404C-D307-4137-B640-AF28A962B2AD
ms.date: 02/15/2018
keywords: ["IOCTL_SMARTCARD_IS_ABSENT IOCTL"]
ms.keywords: IOCTL_SMARTCARD_IS_ABSENT, IOCTL_SMARTCARD_IS_ABSENT control, IOCTL_SMARTCARD_IS_ABSENT control code [Near-Field Proximity Drivers], nfpdrivers.ioctl_smartcard_is_absent, winsmcrd/IOCTL_SMARTCARD_IS_ABSENT
f1_keywords:
 - "winsmcrd/IOCTL_SMARTCARD_IS_ABSENT"
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
- IOCTL_SMARTCARD_IS_ABSENT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SMARTCARD_IS_ABSENT IOCTL


## -description


The <b>IOCTL_SMARTCARD_IS_ABSENT</b> 
   control code returns immediately with STATUS_SUCCESS if no smart card is currently detected. If smart cards are detected, the IOCTL needs to be pended by the driver and it needs to complete the request on card departure. Closing the file handle automatically unsubscribes the event.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length








### -output-buffer

None.


### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

<b>Irp->IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful. Possible error codes are:

<table>
<tr>
<th>Return Code</th>
<th>Description</th>
</tr>
<tr>
<td>STATUS_PENDING</td>
<td>This code is returned when the attribute ID is SCARD_ATTR_DEVICE_IN_USE.</td>
</tr>
<tr>
<td>STATUS_DEVICE_BUSY</td>
<td>This code is returned if the operation is already waiting for the absent event.</td>
</tr>
<tr>
<td>STATUS_INVALID_DEVICE_STATE</td>
<td>This code is returned if the device cannot accept the request.
</td>
</tr>
<tr>
<td>STATUS_INVALID_PARAMETER</td>
<td>This code is returned when the input or output buffers are invalid.</td>
</tr>
<tr>
<td>STATUS_DEVICE_POWERED_OFF</td>
<td>This code is returned when the proximity radio control is off.</td>
</tr>
</table>
 


## -remarks



The following actions are required when using this IOCTL:<ul>
<li>

The driver must support CancelIo on this pended IOCTL.

</li>
<li>It is a power-managed request. The pended IOCTL will keep the driver in D0 power state.</li>
</ul>





## -see-also




<a href="https://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/nfc/design-guide-smart-card">Smart card design guide</a>
 

 

