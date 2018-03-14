---
UID: NS:ntddcdvd._AACS_CERTIFICATE
title: "_AACS_CERTIFICATE"
author: windows-driver-content
description: The AACS_CERTIFICATE structure contains a cryptographically random 160-bit value, followed by a 92-byte certificate.
old-location: storage\aacs_certificate.htm
old-project: storage
ms.assetid: 591d8f63-ab3e-48b7-8fe4-98dcdf9464f1
ms.author: windowsdriverdev
ms.date: 2/26/2018
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddcdvd.h
api_name:
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



 

 


