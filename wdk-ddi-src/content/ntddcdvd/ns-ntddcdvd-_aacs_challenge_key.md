---
UID: NS:ntddcdvd._AACS_CHALLENGE_KEY
title: "_AACS_CHALLENGE_KEY"
author: windows-driver-content
description: The AACS_CHALLENGE_KEY structure contains the challenge key that the device sends to the host.
old-location: storage\aacs_challenge_key.htm
old-project: storage
ms.assetid: b1eb7978-cbfc-4ffd-b345-a320e9152f03
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: ntddcdvd/PAACS_CHALLENGE_KEY, structs-DVD_7a8e1eeb-73f5-4d10-83c6-13bac3130c91.xml, AACS_CHALLENGE_KEY, PAACS_CHALLENGE_KEY, AACS_CHALLENGE_KEY structure [Storage Devices], ntddcdvd/AACS_CHALLENGE_KEY, _AACS_CHALLENGE_KEY, *PAACS_CHALLENGE_KEY, storage.aacs_challenge_key, PAACS_CHALLENGE_KEY structure pointer [Storage Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	ntddcdvd.h
apiname:
-	AACS_CHALLENGE_KEY
product: Windows
targetos: Windows
req.typenames: AACS_CHALLENGE_KEY, *PAACS_CHALLENGE_KEY
---

# _AACS_CHALLENGE_KEY structure


## -description


The AACS_CHALLENGE_KEY structure contains the challenge key that the device sends to the host.


## -syntax


````
typedef struct _AACS_CHALLENGE_KEY {
  UCHAR EllipticCurvePoint[40];
  UCHAR Signature[40];
} AACS_CHALLENGE_KEY, *PAACS_CHALLENGE_KEY;
````


## -struct-fields




### -field EllipticCurvePoint

The elliptical curve (ECC) point data.


### -field Signature

The signature that the client uses to verify that the ECC point is valid for the current Advanced Access Content System (AACS) authentication sequence.


## -remarks



Clients retrieve the Advanced Access Content System (AACS) challenge key with an <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_get_challenge_key.md">IOCTL_AACS_GET_CHALLENGE_KEY</a> request. Clients send an AACS challenge key to the logical unit in an <a href="..\ntddcdvd\ns-ntddcdvd-_aacs_send_challenge_key.md">AACS_SEND_CHALLENGE_KEY</a> structure with an <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_send_challenge_key.md">IOCTL_AACS_SEND_CHALLENGE_KEY</a>. 




## -see-also

<a href="..\ntddcdvd\ns-ntddcdvd-_aacs_send_challenge_key.md">AACS_SEND_CHALLENGE_KEY</a>



<a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_get_challenge_key.md">IOCTL_AACS_GET_CHALLENGE_KEY</a>



<a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_send_challenge_key.md">IOCTL_AACS_SEND_CHALLENGE_KEY</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AACS_CHALLENGE_KEY structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

