---
UID: NI:winsmcrd.IOCTL_SMARTCARD_GET_LAST_ERROR
title: IOCTL_SMARTCARD_GET_LAST_ERROR
author: windows-driver-content
description: The IOCTL_SMARTCARD_GET_LAST_ERROR request retrieves the error code of the most previous operation because there is no option to return an error code immediately after an overlapped operation is complete.
old-location: smartcrd\ioctl_smartcard_get_last_error.htm
old-project: smartcrd
ms.assetid: eb482764-3a78-498b-985c-1efc77000291
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IOCTL_SMARTCARD_GET_LAST_ERROR, IOCTL_SMARTCARD_GET_LAST_ERROR control code [Smart Card Reader Devices], scioctls_f53172a6-95cb-4d50-9a2b-bccc623bf85b.xml, smartcrd.ioctl_smartcard_get_last_error, winsmcrd/IOCTL_SMARTCARD_GET_LAST_ERROR
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
-	Winsmcrd.h
api_name:
-	IOCTL_SMARTCARD_GET_LAST_ERROR
product: Windows
targetos: Windows
req.typenames: PRINTER_EVENT_ATTRIBUTES_INFO, *PPRINTER_EVENT_ATTRIBUTES_INFO
req.product: Windows 10 or later.
---

# IOCTL_SMARTCARD_GET_LAST_ERROR IOCTL


## -description



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

<b>Irp-&gt;IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful, and must be returned when using this IOCTL. 

Be aware that when your driver uses the smart card driver library, you should store the result of the most previously overlapped operation in the smart card extension. ion. The library will use your stored value to answer this call automatically.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn905519">IOCTL_SMARTCARD_GET_STATE</a>
 

 

