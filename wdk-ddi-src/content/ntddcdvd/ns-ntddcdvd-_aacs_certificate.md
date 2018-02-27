---
UID: NS:ntddcdvd._AACS_CERTIFICATE
title: "_AACS_CERTIFICATE"
author: windows-driver-content
description: The AACS_CERTIFICATE structure contains a cryptographically random 160-bit value, followed by a 92-byte certificate.
old-location: storage\aacs_certificate.htm
old-project: storage
ms.assetid: 591d8f63-ab3e-48b7-8fe4-98dcdf9464f1
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PAACS_CERTIFICATE, AACS_CERTIFICATE, AACS_CERTIFICATE structure [Storage Devices], PAACS_CERTIFICATE, PAACS_CERTIFICATE structure pointer [Storage Devices], _AACS_CERTIFICATE, ntddcdvd/AACS_CERTIFICATE, ntddcdvd/PAACS_CERTIFICATE, storage.aacs_certificate, structs-DVD_0eedee44-0be8-462e-84ac-e5efbc37fc82.xml"
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
-	AACS_CERTIFICATE
product: Windows
targetos: Windows
req.typenames: AACS_CERTIFICATE, *PAACS_CERTIFICATE
---

# _AACS_CERTIFICATE structure


## -description


The AACS_CERTIFICATE structure contains a cryptographically random 160-bit value, followed by a 92-byte certificate.


## -syntax


````
typedef struct _AACS_CERTIFICATE {
  UCHAR Nonce[20];
  UCHAR Certificate[92];
} AACS_CERTIFICATE, *PAACS_CERTIFICATE;
````


## -struct-fields




### -field Nonce

A cryptographically random 160-bit nonce value.


### -field Certificate

A 92-byte certificate.


## -remarks



Clients retrieve an Advanced Access Content System (AACS) certificate with an <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_get_certificate.md">IOCTL_AACS_GET_CERTIFICATE</a> request. Clients send certificates in a <a href="..\ntddcdvd\ns-ntddcdvd-_aacs_send_certificate.md">AACS_SEND_CERTIFICATE</a> structure with an <a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_send_certificate.md">IOCTL_AACS_SEND_CERTIFICATE</a> request.




## -see-also

<a href="..\ntddcdvd\ni-ntddcdvd-ioctl_aacs_get_certificate.md">IOCTL_AACS_GET_CERTIFICATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AACS_CERTIFICATE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

