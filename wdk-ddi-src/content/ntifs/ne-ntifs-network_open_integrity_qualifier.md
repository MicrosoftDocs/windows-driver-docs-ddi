---
UID: NE:ntifs.NETWORK_OPEN_INTEGRITY_QUALIFIER
title: NETWORK_OPEN_INTEGRITY_QUALIFIER
author: windows-driver-content
description: The NETWORK_OPEN_INTEGRITY_QUALIFIER enumeration type contains values that identify the kind of integrity restriction to attach to a file.
old-location: ifsk\network_open_integrity_qualifier.htm
old-project: ifsk
ms.assetid: 6a51ee2e-2df6-44f4-8e95-776851d743a6
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.network_open_integrity_qualifier, NetworkOpenIntegritySigned, NetworkOpenIntegrityNone, NetworkOpenIntegrityEncrypted, NETWORK_OPEN_INTEGRITY_QUALIFIER, ntifs/NetworkOpenIntegritySigned, NetworkOpenIntegrityMaximum, ntifs/NetworkOpenIntegrityNone, NetworkOpenIntegrityAny, ntifs/NETWORK_OPEN_INTEGRITY_QUALIFIER, NETWORK_OPEN_INTEGRITY_QUALIFIER enumeration [Installable File System Drivers], ECP_Structures_e5f36510-f63f-47bc-941c-690d51ea0608.xml, ntifs/NetworkOpenIntegrityAny, ntifs/NetworkOpenIntegrityMaximum, ntifs/NetworkOpenIntegrityEncrypted
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	ntifs.h
apiname: 
-	NETWORK_OPEN_INTEGRITY_QUALIFIER
product: Windows
targetos: Windows
req.typenames: NETWORK_OPEN_INTEGRITY_QUALIFIER
---

# NETWORK_OPEN_INTEGRITY_QUALIFIER enumeration


## -description


The NETWORK_OPEN_INTEGRITY_QUALIFIER enumeration type contains values that identify the kind of integrity restriction to attach to a file.


## -syntax


````
typedef enum  { 
  NetworkOpenIntegrityAny        = 0,
  NetworkOpenIntegrityNone       = 1,
  NetworkOpenIntegritySigned     = 2,
  NetworkOpenIntegrityEncrypted  = 3,
  NetworkOpenIntegrityMaximum    = 4
} NETWORK_OPEN_INTEGRITY_QUALIFIER;
````


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

