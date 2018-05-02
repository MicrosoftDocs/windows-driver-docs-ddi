---
UID: NI:winsmcrd.IOCTL_SMARTCARD_EJECT
title: IOCTL_SMARTCARD_EJECT
author: windows-driver-content
description: The IOCTL_SMARTCARD_EJECT request ejects the currently inserted smart card from the smart card reader.
old-location: smartcrd\ioctl_smartcard_eject.htm
old-project: smartcrd
ms.assetid: 58bdd794-9061-4aae-a9a6-523db4e2e360
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: IOCTL_SMARTCARD_EJECT, IOCTL_SMARTCARD_EJECT control, IOCTL_SMARTCARD_EJECT control code [Smart Card Reader Devices], scioctls_e12f239a-b997-4af6-bace-92e9c65c88b6.xml, smartcrd.ioctl_smartcard_eject, winsmcrd/IOCTL_SMARTCARD_EJECT
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
-	IOCTL_SMARTCARD_EJECT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_SMARTCARD_EJECT IOCTL


## -description



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

<b>Irp-&gt;IoStatus.Status</b> is set to <b>STATUS_SUCCESS</b> if the request is successful. Possible error codes are:

<table>
<tr>
<th>Return Code</th>
<th>Description</th>
</tr>
<tr>
<td>STATUS_NO_MEDIA</td>
<td>No smart card is in the reader.</td>
</tr>
<tr>
<td>STATUS_NOT_SUPPORTED</td>
<td> Reader does not support smart card eject.</td>
</tr>
<tr>
<td>STATUS_IO_TIMEOUT</td>
<td>Operation timed out.</td>
</tr>
</table>
 

