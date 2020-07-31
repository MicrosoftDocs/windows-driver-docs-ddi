---
UID: NI:winsmcrd.IOCTL_SMARTCARD_SET_ATTRIBUTE
title: IOCTL_SMARTCARD_SET_ATTRIBUTE (winsmcrd.h)
description: The IOCTL_SMARTCARD_SET_ATTRIBUTE control code sets an attribute and returns STATUS_SUCCESS on SCARD_ATTR_DEVICE_IN_USE; otherwise, it returns STATUS_NOT_SUPPORTED.
old-location: nfpdrivers\ioctl_smartcard_set_attribute.htm
tech.root: nfpdrivers
ms.assetid: 48B5F00C-1DDD-488C-8269-E52DF366D552
ms.date: 02/15/2018
keywords: ["IOCTL_SMARTCARD_SET_ATTRIBUTE IOCTL"]
ms.keywords: IOCTL_SMARTCARD_SET_ATTRIBUTE, IOCTL_SMARTCARD_SET_ATTRIBUTE control, IOCTL_SMARTCARD_SET_ATTRIBUTE control code [Near-Field Proximity Drivers], nfpdrivers.ioctl_smartcard_set_attribute, winsmcrd/IOCTL_SMARTCARD_SET_ATTRIBUTE
f1_keywords:
 - "winsmcrd/IOCTL_SMARTCARD_SET_ATTRIBUTE"
 - "IOCTL_SMARTCARD_SET_ATTRIBUTE"
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
- IOCTL_SMARTCARD_SET_ATTRIBUTE
targetos: Windows
req.typenames: 
---

# IOCTL_SMARTCARD_SET_ATTRIBUTE IOCTL


## -description


The <b>IOCTL_SMARTCARD_SET_ATTRIBUTE</b> 
   control code sets an attribute and returns STATUS_SUCCESS on SCARD_ATTR_DEVICE_IN_USE; otherwise, it returns STATUS_NOT_SUPPORTED.


## -ioctlparameters




### -input-buffer

(DWORD) contains the attribute identifier.


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
<td>STATUS_NOT_SUPPORTED</td>
<td>This code is returned when the attribute ID is  not SCARD_ATTR_DEVICE_IN_USE.
</td>
</tr>
<tr>
<td>STATUS_DEVICE_POWERED_OFF</td>
<td>This code is returned if the proximity radio control is off.</td>
</tr>
</table>
 


## -see-also




<a href="https://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/nfc/design-guide-smart-card">Smart card design guide</a>
 

 

