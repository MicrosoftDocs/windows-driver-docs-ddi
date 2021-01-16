---
UID: NS:ntddcdvd._AACS_BINDING_NONCE
title: _AACS_BINDING_NONCE (ntddcdvd.h)
description: The AACS_BINDING_NONCE structure contains the binding nonce.
old-location: storage\aacs_binding_nonce.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["AACS_BINDING_NONCE structure"]
ms.keywords: "*PAACS_BINDING_NONCE, AACS_BINDING_NONCE, AACS_BINDING_NONCE structure [Storage Devices], PAACS_BINDING_NONCE, PAACS_BINDING_NONCE structure pointer [Storage Devices], _AACS_BINDING_NONCE, ntddcdvd/AACS_BINDING_NONCE, ntddcdvd/PAACS_BINDING_NONCE, storage.aacs_binding_nonce, structs-DVD_4420e26a-681e-4942-9f90-699bcd80b37f.xml"
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
req.typenames: AACS_BINDING_NONCE, *PAACS_BINDING_NONCE
f1_keywords:
 - _AACS_BINDING_NONCE
 - ntddcdvd/_AACS_BINDING_NONCE
 - PAACS_BINDING_NONCE
 - ntddcdvd/PAACS_BINDING_NONCE
 - AACS_BINDING_NONCE
 - ntddcdvd/AACS_BINDING_NONCE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddcdvd.h
api_name:
 - _AACS_BINDING_NONCE
 - PAACS_BINDING_NONCE
 - AACS_BINDING_NONCE
---

# _AACS_BINDING_NONCE structure


## -description

The AACS_BINDING_NONCE structure contains the binding nonce.

## -struct-fields

### -field BindingNonce

The binding nonce for the requested logical block address(es) (LBAs).

### -field MAC

A message authentication code (MAC) that clients can use to verify that the binding nonce is for the current Advanced Access Content System (AACS) Authentication sequence.

## -remarks

Clients retrieve the binding nonce with an <a href="/windows-hardware/drivers/ddi/ntddcdvd/ni-ntddcdvd-ioctl_aacs_read_binding_nonce">IOCTL_AACS_READ_BINDING_NONCE</a> request or an <a href="/windows-hardware/drivers/ddi/ntddcdvd/ni-ntddcdvd-ioctl_aacs_generate_binding_nonce">IOCTL_AACS_GENERATE_BINDING_NONCE</a> request.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddcdvd/ni-ntddcdvd-ioctl_aacs_generate_binding_nonce">IOCTL_AACS_GENERATE_BINDING_NONCE</a>



<a href="/windows-hardware/drivers/ddi/ntddcdvd/ni-ntddcdvd-ioctl_aacs_read_binding_nonce">IOCTL_AACS_READ_BINDING_NONCE</a>

