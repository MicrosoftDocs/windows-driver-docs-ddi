---
UID: NS:ntddcdvd._AACS_CERTIFICATE
title: _AACS_CERTIFICATE (ntddcdvd.h)
description: The AACS_CERTIFICATE structure contains a cryptographically random 160-bit value, followed by a 92-byte certificate.
old-location: storage\aacs_certificate.htm
tech.root: storage
ms.assetid: 591d8f63-ab3e-48b7-8fe4-98dcdf9464f1
ms.date: 03/29/2018
keywords: ["AACS_CERTIFICATE structure"]
ms.keywords: "*PAACS_CERTIFICATE, AACS_CERTIFICATE, AACS_CERTIFICATE structure [Storage Devices], PAACS_CERTIFICATE, PAACS_CERTIFICATE structure pointer [Storage Devices], _AACS_CERTIFICATE, ntddcdvd/AACS_CERTIFICATE, ntddcdvd/PAACS_CERTIFICATE, storage.aacs_certificate, structs-DVD_0eedee44-0be8-462e-84ac-e5efbc37fc82.xml"
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
targetos: Windows
req.typenames: AACS_CERTIFICATE, *PAACS_CERTIFICATE
f1_keywords:
 - _AACS_CERTIFICATE
 - ntddcdvd/_AACS_CERTIFICATE
 - PAACS_CERTIFICATE
 - ntddcdvd/PAACS_CERTIFICATE
 - AACS_CERTIFICATE
 - ntddcdvd/AACS_CERTIFICATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddcdvd.h
api_name:
 - AACS_CERTIFICATE
---

# _AACS_CERTIFICATE structure


## -description

The AACS_CERTIFICATE structure contains a cryptographically random 160-bit value, followed by a 92-byte certificate.

## -struct-fields

### -field Nonce

A cryptographically random 160-bit nonce value.

### -field Certificate

A 92-byte certificate.

## -remarks

Clients retrieve an Advanced Access Content System (AACS) certificate with an <a href="/windows-hardware/drivers/ddi/ntddcdvd/ni-ntddcdvd-ioctl_aacs_get_certificate">IOCTL_AACS_GET_CERTIFICATE</a> request. Clients send certificates in a <a href="/windows-hardware/drivers/ddi/ntddcdvd/ns-ntddcdvd-_aacs_send_certificate">AACS_SEND_CERTIFICATE</a> structure with an <a href="/windows-hardware/drivers/ddi/ntddcdvd/ni-ntddcdvd-ioctl_aacs_send_certificate">IOCTL_AACS_SEND_CERTIFICATE</a> request.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddcdvd/ni-ntddcdvd-ioctl_aacs_get_certificate">IOCTL_AACS_GET_CERTIFICATE</a>