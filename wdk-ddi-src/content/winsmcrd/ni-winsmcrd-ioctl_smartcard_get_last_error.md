---
UID: NI:winsmcrd.IOCTL_SMARTCARD_GET_LAST_ERROR
title: IOCTL_SMARTCARD_GET_LAST_ERROR
author: windows-driver-content
description: The IOCTL_SMARTCARD_GET_LAST_ERROR request retrieves the error code of the most previous operation because there is no option to return an error code immediately after an overlapped operation is complete.
old-location: smartcrd\ioctl_smartcard_get_last_error.htm
old-project: smartcrd
ms.assetid: eb482764-3a78-498b-985c-1efc77000291
ms.author: windowsdriverdev
ms.date: 12/14/2017
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
req.alt-api: IOCTL_SMARTCARD_GET_LAST_ERROR
req.alt-loc: Winsmcrd.h
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

# IOCTL_SMARTCARD_GET_LAST_ERROR IOCTL



## -description

The IOCTL_SMARTCARD_GET_LAST_ERROR request retrieves the error code of the most previous operation because there is no option to return an error code immediately after an overlapped operation is complete.



The IOCTL_SMARTCARD_GET_LAST_ERROR request retrieves the error code of the most previous operation because there is no option to return an error code immediately after an overlapped operation is complete.



## -ioctlparameters

### -input-buffer
<i>DiocParams-&gt;cbOutBuffer</i>

Contains the size of the output buffer. Must be at least <b>sizeof</b>(ULONG).


### -input-buffer-length

<text></text>

### -output-buffer
<i>DiocParams-&gt;lpvOutBuffer</i>

Receives the error code.

<i>DiocParams-&gt;lpcbBytesReturned</i>

Must be set to <b>sizeof</b>(ULONG).


### -output-buffer-length

<text></text>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
<b>Irp-&gt;IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful, and must be returned when using this IOCTL. 

Be aware that when your driver uses the smart card driver library, you should store the result of the most previously overlapped operation in the smart card extension. ion. The library will use your stored value to answer this call automatically.


## -remarks


## -see-also
<dl>
<dt>
<a href="..\winsmcrd\ni-winsmcrd-ioctl_smartcard_get_state.md">IOCTL_SMARTCARD_GET_STATE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [smartcrd\smartcrd]:%20IOCTL_SMARTCARD_GET_LAST_ERROR control code%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

