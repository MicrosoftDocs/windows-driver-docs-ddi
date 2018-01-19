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
req.alt-api: IOCTL_SMARTCARD_POWER
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

# IOCTL_SMARTCARD_POWER IOCTL



## -description
Windows may require a driver to have this IOCTL to be NOP and return success.

The <b>IOCTL_SMARTCARD_POWER</b> 
   control code  puts the smart card into one of the following power modes:

 



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
I/O Status block
<b>Irp-&gt;IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful. Possible error codes are:

 


## -remarks
Virtual power is set to TRUE for COLD_RESET and WARM_RESET; otherwise, virtual power is set to FALSE.


## -see-also
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a></dt>
<dt><a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/design-guide-smart-card">Smart card design guide</a></dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20IOCTL_SMARTCARD_POWER control code%20 RELEASE:%20(12/18/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

