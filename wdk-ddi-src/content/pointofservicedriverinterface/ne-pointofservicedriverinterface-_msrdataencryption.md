---
UID: NE:pointofservicedriverinterface._MsrDataEncryption
title: _MsrDataEncryption (pointofservicedriverinterface.h)
description: This enumeration defines the kind of encryption algorithm supported by the magnetic stripe reader (MSR).
old-location: pos\msrdataencryption.htm
tech.root: pos
ms.date: 02/23/2018
keywords: ["MsrDataEncryption enumeration"]
ms.keywords: MsrDataEncryption, MsrDataEncryption enumeration, MsrDataEncryption_3DEA_DUKPT, MsrDataEncryption_AES, MsrDataEncryption_ExtendedBase, MsrDataEncryption_None, _MsrDataEncryption, pointofservicedriverinterface/MsrDataEncryption, pointofservicedriverinterface/MsrDataEncryption_3DEA_DUKPT, pointofservicedriverinterface/MsrDataEncryption_AES, pointofservicedriverinterface/MsrDataEncryption_ExtendedBase, pointofservicedriverinterface/MsrDataEncryption_None, pos.msrdataencryption
req.header: pointofservicedriverinterface.h
req.include-header: Pointofservicedriverinterface.h
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
req.typenames: MsrDataEncryption
f1_keywords:
 - _MsrDataEncryption
 - pointofservicedriverinterface/_MsrDataEncryption
 - MsrDataEncryption
 - pointofservicedriverinterface/MsrDataEncryption
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pointofservicedriverinterface.h
api_name:
 - _MsrDataEncryption
 - MsrDataEncryption
---

# _MsrDataEncryption enumeration


## -description

This enumeration defines the kind of encryption algorithm supported by the magnetic stripe reader (MSR).

## -enum-fields

### -field MsrDataEncryption_None

Indicates no encryption algorithm.

### -field MsrDataEncryption_3DEA_DUKPT

The Triple Data Encryption Standard (DES) Derived Unique Key Per Transaction (DUKPT) encryption algorithm.

### -field MsrDataEncryption_AES

The Advanced Encryption Standard (AES).

### -field MsrDataEncryption_ExtendedBase

A vendor-specific encryption algorithm. Service-specific values begin at 0x01000000 and are reserved for additional encryption algorithms.

