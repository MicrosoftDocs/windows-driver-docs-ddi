---
UID: NS:objectheader._NDIS_OBJECT_HEADER
title: NDIS_OBJECT_HEADER
ms.date: 11/30/2020
ms.topic: language-reference
targetos: Windows
description: The NDIS_OBJECT_HEADER structure packages the object type, version, and size information that is required in many NDIS 6.0 structures.
tech.root: netvista
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ndis/objectheader.h
req.include-header: ndis.h
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.target-type: 
req.typenames: NDIS_OBJECT_HEADER, *PNDIS_OBJECT_HEADER
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - objectheader.h
api_name:
 - _NDIS_OBJECT_HEADER
 - PNDIS_OBJECT_HEADER
 - NDIS_OBJECT_HEADER
f1_keywords:
 - _NDIS_OBJECT_HEADER
 - objectheader/_NDIS_OBJECT_HEADER
 - PNDIS_OBJECT_HEADER
 - objectheader/PNDIS_OBJECT_HEADER
 - NDIS_OBJECT_HEADER
 - objectheader/NDIS_OBJECT_HEADER
dev_langs:
 - c++
---

# _NDIS_OBJECT_HEADER structure


## -description

The NDIS_OBJECT_HEADER structure packages the object type, version, and size information that is
  required in many NDIS 6.0 structures.

## -struct-fields

### -field Type

The type of NDIS object that a structure describes. Use this member to identify the type of
     structure in a memory dump.

### -field Revision

The revision number of the structure. Every NDIS structure that has an NDIS_OBJECT_HEADER member
     has a revision number that applies to the NDIS structure exclusively. This allows NDIS drivers to
     support multiple versions of the same structure. For example, a driver can check the 
     <b>Revision</b> member value at run time and use the appropriate version of the structure.

### -field Size

The total size, in bytes, of the NDIS object structure that includes the NDIS_OBJECT_HEADER
     member. This size includes the size of the NDIS_OBJECT_HEADER member and the other members of the
     structure.

## -remarks

The reference page for every structure, that has an NDIS_OBJECT_HEADER structure as a member, defines
    values for the 
    <b>Type</b>, 
    <b>Revision</b>, and 
    <b>Size</b> members for that structure.



