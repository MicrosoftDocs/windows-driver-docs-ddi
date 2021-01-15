---
UID: NS:gnssdriver.__unnamed_struct_41
title: GNSS_SUPL_CERT_CONFIG (gnssdriver.h)
description: This structure contains SUPL certificate information.
old-location: gnss\gnss_supl_cert_config.htm
tech.root: gnss
ms.date: 11/03/2020
keywords: ["GNSS_SUPL_CERT_CONFIG structure"]
ms.keywords: "*PGNSS_SUPL_CERT_CONFIG, GNSS_SUPL_CERT_CONFIG, GNSS_SUPL_CERT_CONFIG structure [Sensor Devices], PGNSS_SUPL_CERT_CONFIG, PGNSS_SUPL_CERT_CONFIG structure pointer [Sensor Devices], gnss.gnss_supl_cert_config, gnssdriver/GNSS_SUPL_CERT_CONFIG, gnssdriver/PGNSS_SUPL_CERT_CONFIG"
req.header: gnssdriver.h
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
req.typenames: GNSS_SUPL_CERT_CONFIG, *PGNSS_SUPL_CERT_CONFIG
f1_keywords:
 - PGNSS_SUPL_CERT_CONFIG
 - gnssdriver/PGNSS_SUPL_CERT_CONFIG
 - GNSS_SUPL_CERT_CONFIG
 - gnssdriver/GNSS_SUPL_CERT_CONFIG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - gnssdriver.h
api_name:
 - PGNSS_SUPL_CERT_CONFIG
 - GNSS_SUPL_CERT_CONFIG
---

# GNSS_SUPL_CERT_CONFIG structure


## -description

This structure contains SUPL certificate information.

## -struct-fields

### -field Size

Structure size.

### -field Version

Version number.

### -field CertAction

A [GNSS_SUPL_CERT_ACTION](./ne-gnssdriver-gnss_supl_cert_action.md) enumeration value that specifies the action to take on the certificate.

| Action | Description |
|--|--|
| GNSS_SUPL_CERT_INJECT | Inject the certificate. |
| GNSS_SUPL_CERT_DELETE | Delete the certificate specified by **SuplCertName**. The values of **CertSize** and **CertData** are ignored. |
| GNSS_SUPL_CERT_PURGE | Delete all the certificates injected to the GNSS driver previously. The values of **SuplCertName** , **CertSize**, and **CertData** are ignored. |

### -field SuplCertName

String containing the certificate name.

### -field CertSize

The size of the certificate in bytes.

### -field Unused

Padding buffer.

### -field CertData

The binary content of the certificate.  The total size of the bytes is defined by **CertSize**. The certificate is Base64 encoded.

