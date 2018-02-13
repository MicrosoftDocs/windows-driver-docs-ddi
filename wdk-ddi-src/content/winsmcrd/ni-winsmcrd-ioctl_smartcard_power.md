---
UID: NI:winsmcrd.IOCTL_SMARTCARD_POWER
title: IOCTL_SMARTCARD_POWER
author: windows-driver-content
description: Windows may require a driver to have this IOCTL to be NOP and return success.
old-location: nfpdrivers\ioctl_smartcard_power.htm
old-project: nfpdrivers
ms.assetid: 1B6F95FB-E7DC-4D36-A319-F5EB576F8D7A
ms.author: windowsdriverdev
ms.date: 12/18/2017
ms.keywords: nfpdrivers.ioctl_smartcard_power, IOCTL_SMARTCARD_POWER control code [Near-Field Proximity Drivers], IOCTL_SMARTCARD_POWER, winsmcrd/IOCTL_SMARTCARD_POWER
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
-	IOCTL_SMARTCARD_POWER
product: Windows
targetos: Windows
req.typenames: DOT11_WPS_DEVICE_NAME, *PDOT11_WPS_DEVICE_NAME
req.product: Windows 10 or later.
---

# IOCTL_SMARTCARD_POWER IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

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



<text></text>




### -output-buffer

None.


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

<a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/design-guide-smart-card">Smart card design guide</a>



<a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20IOCTL_SMARTCARD_POWER control code%20 RELEASE:%20(12/18/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

