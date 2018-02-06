---
UID: NI:ntddcdvd.IOCTL_AACS_GET_CHALLENGE_KEY
title: IOCTL_AACS_GET_CHALLENGE_KEY
author: windows-driver-content
description: Queries the logical unit for the device's challenge key. The challenge key consists of a point on an elliptic curve and its associated signature.
old-location: storage\ioctl_aacs_get_challenge_key.htm
old-project: storage
ms.assetid: 97c43a15-e120-44bd-8a5e-40b80aba646d
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.ioctl_aacs_get_challenge_key, IOCTL_AACS_GET_CHALLENGE_KEY control code [Storage Devices], IOCTL_AACS_GET_CHALLENGE_KEY, ntddcdvd/IOCTL_AACS_GET_CHALLENGE_KEY, k307_f500a9e4-ea44-4089-bfa0-8215635a11c6.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddcdvd.h
req.include-header: Ntddcdvd.h
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
-	Ntddcdvd.h
apiname:
-	IOCTL_AACS_GET_CHALLENGE_KEY
product: Windows
targetos: Windows
req.typenames: "*PDVD_STRUCTURE_FORMAT, DVD_STRUCTURE_FORMAT"
---

# IOCTL_AACS_GET_CHALLENGE_KEY IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


Queries the logical unit for the device's challenge key. The challenge key consists of a point on an elliptic curve and its associated signature. 


## -ioctlparameters




### -input-buffer

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains a value of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff553743">DVD_SESSION_ID</a> that specifies an Authentication Grant Identifier (AGID). The AGID identifies the secure session.


### -input-buffer-length

Length of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553743">DVD_SESSION_ID</a>.


### -output-buffer

The buffer at <b>Irp-&gt;AssociatedIrp.SystemBuffer</b> contains the drive challenge key with a format of <a href="..\ntddcdvd\ns-ntddcdvd-_aacs_challenge_key.md">AACS_CHALLENGE_KEY</a>. 


### -output-buffer-length

Length of an <a href="..\ntddcdvd\ns-ntddcdvd-_aacs_challenge_key.md">AACS_CHALLENGE_KEY</a>.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS or possibly STATUS_INSUFFICIENT_RESOURCES.


## -remarks


 The IOCTL_AACS_GET_CHALLENGE_KEY request corresponds to the step in the Advanced Access Content System (AACS) authentication algorithm (AACS-Auth) in which the drive provides the host with a point on the curve. For a complete description of AACS-Auth, see the <i>Advanced Access Content System, Introduction and Common Cryptographic Elements</i> specification that is published by Advanced Access Content System Licensing Administrator (AACS LA).


