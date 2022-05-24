---
UID: NS:ntifs._SEC_CERTIFICATE_REQUEST_CONTEXT
tech.root: ifsk
title: SEC_CERTIFICATE_REQUEST_CONTEXT
ms.date: 05/24/2022
targetos: Windows
description: Learn more about the SEC_CERTIFICATE_REQUEST_CONTEXT structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 22H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: SEC_CERTIFICATE_REQUEST_CONTEXT, *PSEC_CERTIFICATE_REQUEST_CONTEXT
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _SEC_CERTIFICATE_REQUEST_CONTEXT
 - PSEC_CERTIFICATE_REQUEST_CONTEXT
 - SEC_CERTIFICATE_REQUEST_CONTEXT
f1_keywords:
 - _SEC_CERTIFICATE_REQUEST_CONTEXT
 - ntifs/_SEC_CERTIFICATE_REQUEST_CONTEXT
 - PSEC_CERTIFICATE_REQUEST_CONTEXT
 - ntifs/PSEC_CERTIFICATE_REQUEST_CONTEXT
 - SEC_CERTIFICATE_REQUEST_CONTEXT
 - ntifs/SEC_CERTIFICATE_REQUEST_CONTEXT
dev_langs:
 - c++
helpviewer_keywords:
 - _SEC_CERTIFICATE_REQUEST_CONTEXT
---

## -description

The **SEC_CERTIFICATE_REQUEST_CONTEXT** structure provides the certificate request context when [**BufferType**](/windows/win32/api/sspi/ns-sspi-secbuffer) is **SECBUFFER_CERTIFICATE_REQUEST_CONTEXT**.

## -struct-fields

### -field cbCertificateRequestContext

The size in bytes of the **rgCertificateRequestContext** array.

### -field rgCertificateRequestContext

The Transport Layer Security (TLS) 1.3 certificate request context. This context contains the payload bytes of the “opaque certificate_request_context<0..2^8-1>” field in the certificate request message, excluding the one byte size field that the protocol prepends to that buffer, that is stored as **cbCertificateRequestContext**.

## -see-also

[**SecBuffer**](/windows/win32/api/sspi/ns-sspi-secbuffer)
