---
UID: NS:ntifs._SID_AND_ATTRIBUTES_HASH
tech.root: ifsk
title: SID_AND_ATTRIBUTES_HASH
ms.date: 01/10/2023
targetos: Windows
description: Learn more about the SID_AND_ATTRIBUTES_HASH structure.
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
req.target-min-winverclnt: Windows Vista
req.target-min-winversvr: 
req.target-type: 
req.typenames: SID_AND_ATTRIBUTES_HASH, *PSID_AND_ATTRIBUTES_HASH
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _SID_AND_ATTRIBUTES_HASH
 - PSID_AND_ATTRIBUTES_HASH
 - SID_AND_ATTRIBUTES_HASH
f1_keywords:
 - _SID_AND_ATTRIBUTES_HASH
 - ntifs/_SID_AND_ATTRIBUTES_HASH
 - PSID_AND_ATTRIBUTES_HASH
 - ntifs/PSID_AND_ATTRIBUTES_HASH
 - SID_AND_ATTRIBUTES_HASH
 - ntifs/SID_AND_ATTRIBUTES_HASH
dev_langs:
 - c++
helpviewer_keywords:
 - _SID_AND_ATTRIBUTES_HASH
---

## -description

The **SID_AND_ATTRIBUTES_HASH** structure specifies a hash values for the specified array of security identifiers ([SIDs](ns-ntifs-_sid.md)).

## -struct-fields

### -field SidCount

The number of SIDs pointed to by the **SidAttr** parameter.

### -field SidAttr

Pointer to an array of [**SID_AND_ATTRIBUTES**](ns-ntifs-_sid_and_attributes.md) structures that represent SIDs and their attributes.

### -field Hash[SID_HASH_SIZE]

Array of pointers to hash values. These values correspond to the [**SID_AND_ATTRIBUTES**](ns-ntifs-_sid_and_attributes.md) structures pointed to by the **SidAttr** parameter.

The SID_HASH_ENTRY data type is defined in *ntifs.h* as a ULONG_PTR.

The SID_HASH_SIZE array dimension is defined in *ntifs.h* as 32.

## -see-also

[**TOKEN_ACCESS_INFORMATION**](ns-ntifs-token_access_information.md)
