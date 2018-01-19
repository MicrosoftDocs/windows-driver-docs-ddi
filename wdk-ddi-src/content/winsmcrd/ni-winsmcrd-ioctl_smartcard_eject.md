---
UID: NI:winsmcrd.IOCTL_SMARTCARD_EJECT
title: IOCTL_SMARTCARD_EJECT
author: windows-driver-content
description: The IOCTL_SMARTCARD_EJECT request ejects the currently inserted smart card from the smart card reader.
old-location: smartcrd\ioctl_smartcard_eject.htm
old-project: smartcrd
ms.assetid: 58bdd794-9061-4aae-a9a6-523db4e2e360
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
req.alt-api: IOCTL_SMARTCARD_EJECT
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

# IOCTL_SMARTCARD_EJECT IOCTL



## -description

The IOCTL_SMARTCARD_EJECT request ejects the currently inserted smart card from the smart card reader.



The IOCTL_SMARTCARD_EJECT request ejects the currently inserted smart card from the smart card reader.



## -ioctlparameters

### -input-buffer
None 


### -input-buffer-length

<text></text>

### -output-buffer
None 


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
