---
UID: NS:iddcx.IDARG_IN_OPM_GET_CERTIFICATE
title: IDARG_IN_OPM_GET_CERTIFICATE (iddcx.h)
description: Gives information about the OPM certificate.
old-location: display\idarg_in_opm_get_certificate.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["IDARG_IN_OPM_GET_CERTIFICATE structure"]
ms.keywords: IDARG_IN_OPM_GET_CERTIFICATE, IDARG_IN_OPM_GET_CERTIFICATE structure [Display Devices], display.idarg_in_opm_get_certificate, iddcx/IDARG_IN_OPM_GET_CERTIFICATE
req.header: iddcx.h
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IDARG_IN_OPM_GET_CERTIFICATE
 - iddcx/IDARG_IN_OPM_GET_CERTIFICATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iddcx.h
api_name:
 - IDARG_IN_OPM_GET_CERTIFICATE
---

# IDARG_IN_OPM_GET_CERTIFICATE structure


## -description

                 Gives information about the 
             OPM certificate.

## -struct-fields

### -field CertificateType

                     [in] Type of certificate the information request is for.

### -field CertificateBufferSizeInBytes

                     [in] Size of the buffer provided for the driver to copy the certificate to.

### -field pCertificate

                     [out] A pointer to a buffer that the driver copies the certificate to.

