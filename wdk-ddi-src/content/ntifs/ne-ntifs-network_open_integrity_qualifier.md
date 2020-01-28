---
UID: NE:ntifs.NETWORK_OPEN_INTEGRITY_QUALIFIER
title: NETWORK_OPEN_INTEGRITY_QUALIFIER (ntifs.h)
description: The NETWORK_OPEN_INTEGRITY_QUALIFIER enumeration type contains values that identify the kind of integrity restriction to attach to a file.
old-location: ifsk\network_open_integrity_qualifier.htm
tech.root: ifsk
ms.assetid: 6a51ee2e-2df6-44f4-8e95-776851d743a6
ms.date: 04/16/2018
ms.keywords: ECP_Structures_e5f36510-f63f-47bc-941c-690d51ea0608.xml, NETWORK_OPEN_INTEGRITY_QUALIFIER, NETWORK_OPEN_INTEGRITY_QUALIFIER enumeration [Installable File System Drivers], NetworkOpenIntegrityAny, NetworkOpenIntegrityEncrypted, NetworkOpenIntegrityMaximum, NetworkOpenIntegrityNone, NetworkOpenIntegritySigned, ifsk.network_open_integrity_qualifier, ntifs/NETWORK_OPEN_INTEGRITY_QUALIFIER, ntifs/NetworkOpenIntegrityAny, ntifs/NetworkOpenIntegrityEncrypted, ntifs/NetworkOpenIntegrityMaximum, ntifs/NetworkOpenIntegrityNone, ntifs/NetworkOpenIntegritySigned
f1_keywords:
 - "ntifs/NETWORK_OPEN_INTEGRITY_QUALIFIER"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: This enumeration type is available starting with Windows Vista.
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
- ntifs.h
api_name:
- NETWORK_OPEN_INTEGRITY_QUALIFIER
product:
- Windows
targetos: Windows
req.typenames: NETWORK_OPEN_INTEGRITY_QUALIFIER
---

# NETWORK_OPEN_INTEGRITY_QUALIFIER enumeration


## -description


The NETWORK_OPEN_INTEGRITY_QUALIFIER enumeration type contains values that identify the kind of integrity restriction to attach to a file.


## -enum-fields




### -field NetworkOpenIntegrityAny

Indicates that the file has no integrity restrictions. That is, the file has no restrictions about how to sign, encrypt, and so on. 


### -field NetworkOpenIntegrityNone

Indicates that the file is not signed or encrypted. 


### -field NetworkOpenIntegritySigned

Indicates that the file is signed end-to-end. 


### -field NetworkOpenIntegrityEncrypted

Indicates that the file is encrypted end-to-end. 


### -field NetworkOpenIntegrityMaximum

Indicates that the file has the best integrity that is available. 

