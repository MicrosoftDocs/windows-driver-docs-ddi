---
UID: NE:iscsidef.__unnamed_enum_1
title: ISCSI_DIGEST_TYPES (iscsidef.h)
description: The ISCSI_DIGEST_TYPES enumeration indicates the digest type.
old-location: storage\iscsi_digest_types.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["ISCSI_DIGEST_TYPES enumeration"]
ms.keywords: "*PISCSI_DIGEST_TYPES, ISCSI_DIGEST_TYPES, ISCSI_DIGEST_TYPES enumeration [Storage Devices], ISCSI_DIGEST_TYPE_CRC32C, ISCSI_DIGEST_TYPE_NONE, PISCSI_DIGEST_TYPES, PISCSI_DIGEST_TYPES enumeration pointer [Storage Devices], iscsidef/ISCSI_DIGEST_TYPES, iscsidef/ISCSI_DIGEST_TYPE_CRC32C, iscsidef/ISCSI_DIGEST_TYPE_NONE, iscsidef/PISCSI_DIGEST_TYPES, storage.iscsi_digest_types, structs-iSCSI_107b48fe-7dd1-41d3-b329-d82ba0cd13d4.xml"
req.header: iscsidef.h
req.include-header: Iscsidef.h
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
req.typenames: ISCSI_DIGEST_TYPES, *PISCSI_DIGEST_TYPES
f1_keywords:
 - PISCSI_DIGEST_TYPES
 - iscsidef/PISCSI_DIGEST_TYPES
 - ISCSI_DIGEST_TYPES
 - iscsidef/ISCSI_DIGEST_TYPES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - iscsidef.h
api_name:
 - ISCSI_DIGEST_TYPES
---

# ISCSI_DIGEST_TYPES enumeration


## -description

The ISCSI_DIGEST_TYPES enumeration indicates the digest type.

## -enum-fields

### -field ISCSI_DIGEST_TYPE_NONE

There is no usable digest that guarantees data integrity.

### -field ISCSI_DIGEST_TYPE_CRC32C

The digest that guarantees data integrity uses a 32-bit cyclic redundancy check.

