---
UID: NE:iscsicfg.__unnamed_enum_1
title: "*PISCSI_ENCRYPTION_TYPES"
author: windows-driver-content
description: The ISCSI_ENCRYPTION_TYPES enumeration indicates the type of encryption that is supported.
old-location: storage\iscsi_encryption_types.htm
tech.root: storage
ms.assetid: f1c7a13b-511a-4e9d-a0e6-9fb27126b1d2
ms.date: 02/26/2018
ms.keywords: "*PISCSI_ENCRYPTION_TYPES, ISCSI_ENCRYPTION_TYPES, ISCSI_ENCRYPTION_TYPES enumeration [Storage Devices], ISCSI_ENCRYPT_3DES_HMAC_SHA1, ISCSI_ENCRYPT_AES_CTR, ISCSI_ENCRYPT_NONE, PISCSI_ENCRYPTION_TYPES, PISCSI_ENCRYPTION_TYPES enumeration pointer [Storage Devices], iscsicfg/ISCSI_ENCRYPTION_TYPES, iscsicfg/ISCSI_ENCRYPT_3DES_HMAC_SHA1, iscsicfg/ISCSI_ENCRYPT_AES_CTR, iscsicfg/ISCSI_ENCRYPT_NONE, iscsicfg/PISCSI_ENCRYPTION_TYPES, storage.iscsi_encryption_types, structs-iSCSI_64fe17d0-9efb-447c-82f1-19f6d954eb1e.xml"
ms.topic: enum
req.header: iscsicfg.h
req.include-header: Iscsicfg.h
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
-	iscsicfg.h
api_name:
-	ISCSI_ENCRYPTION_TYPES
product:
- Windows
targetos: Windows
req.typenames: ISCSI_ENCRYPTION_TYPES, *PISCSI_ENCRYPTION_TYPES
---

# *PISCSI_ENCRYPTION_TYPES enumeration


## -description


The ISCSI_ENCRYPTION_TYPES enumeration indicates the type of encryption that is supported.


## -syntax


```cpp
typedef enum  {
  ISCSI_ENCRYPT_NONE            = 0,
  ISCSI_ENCRYPT_3DES_HMAC_SHA1  = 1,
  ISCSI_ENCRYPT_AES_CTR         = 2
} ISCSI_ENCRYPTION_TYPES, *PISCSI_ENCRYPTION_TYPES;
```


## -enum-fields




### -field ISCSI_ENCRYPT_NONE

No type of encryption is supported.


### -field ISCSI_ENCRYPT_3DES_HMAC_SHA1

The initiator or target supports triple data encryption standard (DES), hashed message authentication code (HMAC), and the secure hash algorithm, version 1.


### -field ISCSI_ENCRYPT_AES_CTR

The initiator or target supports advanced encryption standard (AES) counter mode (CTR).


## -remarks



The ISCSI_ENCRYPTION_TYPES enumeration is used with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563131">MSiSCSI_SecurityCapabilities WMI Class</a>.




## -see-also

<a href="..\iscsicfg\ns-iscsicfg-_msiscsi_securitycapabilities.md">MSiSCSI_SecurityCapabilities</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563131">MSiSCSI_SecurityCapabilities WMI Class</a>



 

 


