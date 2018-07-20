---
UID: NI:winsmcrd.IOCTL_SMARTCARD_IS_PRESENT
title: IOCTL_SMARTCARD_IS_PRESENT
author: windows-driver-content
description: The IOCTL_SMARTCARD_IS_PRESENT control code detects whether a smart card is currently detected.
old-location: nfpdrivers\ioctl_smartcard_is_present.htm
tech.root: nfpdrivers
ms.assetid: 8EF97A77-7A6A-4FDF-82AA-05481AEA7C28
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_SMARTCARD_IS_PRESENT, IOCTL_SMARTCARD_IS_PRESENT control, IOCTL_SMARTCARD_IS_PRESENT control code [Near-Field Proximity Drivers], nfpdrivers.ioctl_smartcard_is_present, winsmcrd/IOCTL_SMARTCARD_IS_PRESENT
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
-	IOCTL_SMARTCARD_IS_PRESENT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SMARTCARD_IS_PRESENT IOCTL


## -description


The <b>IOCTL_SMARTCARD_IS_PRESENT</b> 
   control code detects whether a smart card is currently detected. If a card is present, it returns immediately with STATUS_SUCCESS. If no smart card is detected, it subscribes to the smart card arrival event and is kept pending. Closing the file handle unsubscribes the event. 


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

<b>Irp-&gt;IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful. Possible error codes are:

<table>
<tr>
<th>Return Code</th>
<th>Description</th>
</tr>
<tr>
<td>STATUS_PENDING</td>
<td>This code is returned if the operation is waiting for the smart card to approach into the radio field.</td>
</tr>
<tr>
<td>STATUS_DEVICE_BUSY</td>
<td>This code is returned if the operation is already waiting for the present event.</td>
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
<li>It is a power-managed request. The pended IOCTL will keep the driver in a D0 power state.</li>
<li>The driver must return STATUS_SUCCESS only for the supported type.</li>
</ul>





## -see-also




<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>



<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/design-guide-smart-card">Smart card design guide</a>
 

 

