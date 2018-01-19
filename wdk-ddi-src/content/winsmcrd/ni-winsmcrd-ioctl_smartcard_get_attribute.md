---
UID: NI:winsmcrd.IOCTL_SMARTCARD_GET_ATTRIBUTE
title: IOCTL_SMARTCARD_GET_ATTRIBUTE
author: windows-driver-content
description: The IOCTL_SMARTCARD_GET_ATTRIBUTE control code queries for smart card attribues.
old-location: nfpdrivers\ioctl_smartcard_get_attribute.htm
old-project: nfpdrivers
ms.assetid: 5B5F4CA1-0E49-4D60-AD78-3294C80844E1
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
req.alt-api: IOCTL_SMARTCARD_GET_ATTRIBUTE
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

# IOCTL_SMARTCARD_GET_ATTRIBUTE IOCTL



## -description
The <b>IOCTL_SMARTCARD_GET_ATTRIBUTE</b> 
   control code queries for smart card attribues. 



## -ioctlparameters

### -input-buffer
(DWORD) contains the attribute tag.


### -input-buffer-length

<text></text>

### -output-buffer
(DWORD) contains the attribute tag.


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
The following actions are required when using this IOCTL:<ul>
<li>

The driver must support CancelIo on this pended IOCTL.

</li>
<li>If this IOCTL is issued when the NFCC is in RF discovery state, the driver needs to put the NFCC into RF idle state, configure the routing table, and restart RF discovery.</li>
</ul>



## -see-also
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?LinkID=785320">Near field communication (NFC) design guide</a></dt>
<dt><a href="https://msdn.microsoft.com/windows/hardware/drivers/nfc/design-guide-smart-card">Smart card design guide</a></dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [nfpdrivers\nfpdrivers]:%20IOCTL_SMARTCARD_GET_ATTRIBUTE control code%20 RELEASE:%20(12/18/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

