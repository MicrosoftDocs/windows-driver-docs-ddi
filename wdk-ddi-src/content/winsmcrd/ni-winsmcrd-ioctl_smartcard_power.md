---
UID: NI:winsmcrd.IOCTL_SMARTCARD_POWER
title: IOCTL_SMARTCARD_POWER (winsmcrd.h)
description: Windows may require a driver to have this IOCTL to be NOP and return success.
old-location: nfpdrivers\ioctl_smartcard_power.htm
tech.root: nfpdrivers
ms.assetid: 1B6F95FB-E7DC-4D36-A319-F5EB576F8D7A
ms.date: 02/15/2018
keywords: ["IOCTL_SMARTCARD_POWER IOCTL"]
ms.keywords: IOCTL_SMARTCARD_POWER, IOCTL_SMARTCARD_POWER control, IOCTL_SMARTCARD_POWER control code [Near-Field Proximity Drivers], nfpdrivers.ioctl_smartcard_power, winsmcrd/IOCTL_SMARTCARD_POWER
f1_keywords:
 - "winsmcrd/IOCTL_SMARTCARD_POWER"
 - "IOCTL_SMARTCARD_POWER"
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
- IOCTL_SMARTCARD_POWER
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SMARTCARD_POWER IOCTL


## -description


Windows may require a driver to have this IOCTL to be NOP and return success.

The <b>IOCTL_SMARTCARD_POWER</b> 
   control code  puts the smart card into one of the following power modes:
<table>
<tr>
<th>Power Mode Setting</th>
<th>Description</th>
</tr>
<tr>
<td>SCARD_COLD_RESET</td>
<td>Sets virtual power that only affects the IOCTL_SMARTCARD_GET_STATE. No impact on the actual reader power states. Returns SCARD_SPECIFIC in IOCTL_SMARTCARD_GET_STATE if the card is present.</td>
</tr>
<tr>
<td>SCARD_WARM_RESET</td>
<td>Sets virtual power that only affects the IOCTL_SMARTCARD_GET_STATE. No impact on the actual reader power states. Returns SCARD_SPECIFIC in IOCTL_SMARTCARD_GET_STATE if the card is present.</td>
</tr>
</table> 


## -ioctlparameters




### -input-buffer

(DWORD) that contains the power state to set.


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
<td>STATUS_NO_MEDIA</td>
<td>This code is returned if no smart card is detected.</td>
</tr>
<tr>
<td>STATUS_INVALID_PARAMETER</td>
<td>This code is returned if the input or output buffer is invalid.</td>
</tr>
<tr>
<td>STATUS_DEVICE_POWERED_OFF</td>
<td>This code is returned if the proximity radio control is off.</td>
</tr>
</table>
 


## -remarks



Virtual power is set to TRUE for COLD_RESET and WARM_RESET; otherwise, virtual power is set to FALSE.




## -see-also




<a href="https://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/nfc/design-guide-smart-card">Smart card design guide</a>
 

 

