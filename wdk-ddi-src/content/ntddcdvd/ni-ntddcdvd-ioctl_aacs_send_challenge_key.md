---
UID: NI:ntddcdvd.IOCTL_AACS_SEND_CHALLENGE_KEY
title: IOCTL_AACS_SEND_CHALLENGE_KEY (ntddcdvd.h)
description: Sends the host's challenge key to the logical unit. The host's challenge key consists of a point on an elliptic curve and its associated signature.
old-location: storage\ioctl_aacs_send_challenge_key.htm
tech.root: storage
ms.assetid: 762776f1-5423-4d02-8b59-de1e9ada8044
ms.date: 03/29/2018
ms.keywords: IOCTL_AACS_SEND_CHALLENGE_KEY, IOCTL_AACS_SEND_CHALLENGE_KEY control, IOCTL_AACS_SEND_CHALLENGE_KEY control code [Storage Devices], k307_064ac0c8-c4f9-4232-a41a-72159ff13fd2.xml, ntddcdvd/IOCTL_AACS_SEND_CHALLENGE_KEY, storage.ioctl_aacs_send_challenge_key
ms.topic: ioctl
f1_keywords:
 - "ntddcdvd/IOCTL_AACS_SEND_CHALLENGE_KEY"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ntddcdvd.h
api_name:
- IOCTL_AACS_SEND_CHALLENGE_KEY
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_AACS_SEND_CHALLENGE_KEY IOCTL


## -description


Sends the host's challenge key to the logical unit. The host's challenge key consists of a point on an elliptic curve and its associated signature. 


## -ioctlparameters




### -input-buffer

The buffer at <b>Irp->AssociatedIrp.SystemBuffer</b> contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddcdvd/ns-ntddcdvd-_aacs_send_challenge_key">AACS_SEND_CHALLENGE_KEY</a> structure.


### -input-buffer-length

Length of an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntddcdvd/ns-ntddcdvd-_aacs_send_challenge_key">AACS_SEND_CHALLENGE_KEY</a> structure.


### -output-buffer

None. 


### -output-buffer-length

None. 


### -in-out-buffer


### -inout-buffer-length


### -status-block

The <b>Information</b> field is set to the number of bytes transferred. The <b>Status</b> field is set to STATUS_SUCCESS or possibly STATUS_INSUFFICIENT_RESOURCES.


## -remarks



The IOCTL_AACS_SEND_CHALLENGE_KEY request corresponds to the step in the Advanced Access Content System (AACS) authentication algorithm (AACS-Auth) in which the host provides the drive a point on the curve. For a complete description of AACS-Auth, see the <i>Advanced Access Content System, Introduction and Common Cryptographic Elements</i> specification that is published by Advanced Access Content System Licensing Administrator (AACS LA). 



