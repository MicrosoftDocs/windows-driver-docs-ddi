---
UID: NS:ntddndis._NDIS_OBJECT_HEADER
title: _NDIS_OBJECT_HEADER
author: windows-driver-content
description: The NDIS_OBJECT_HEADER structure packages the object type, version, and size information that is required in many NDIS 6.0 structures.
old-location: netvista\ndis_object_header.htm
old-project: netvista
ms.assetid: 59d1a9b0-a4d0-4a24-aa2f-2167b0f53caa
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddndis/NDIS_OBJECT_HEADER, PNDIS_OBJECT_HEADER structure pointer [Network Drivers Starting with Windows Vista], NDIS_OBJECT_HEADER, NDIS_OBJECT_HEADER structure [Network Drivers Starting with Windows Vista], ntddndis/PNDIS_OBJECT_HEADER, *PNDIS_OBJECT_HEADER, _NDIS_OBJECT_HEADER, netvista.ndis_object_header, ndis_object_ref_c4593f06-bd96-4bbe-8e94-d8b7b1cf413b.xml, PNDIS_OBJECT_HEADER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
-	ntddndis.h
apiname: 
-	NDIS_OBJECT_HEADER
product: Windows
targetos: Windows
req.typenames: *PNDIS_OBJECT_HEADER, NDIS_OBJECT_HEADER
---

# _NDIS_OBJECT_HEADER structure


## -description


The NDIS_OBJECT_HEADER structure packages the object type, version, and size information that is
  required in many NDIS 6.0 structures.


## -syntax


````
typedef struct _NDIS_OBJECT_HEADER {
  UCHAR  Type;
  UCHAR  Revision;
  USHORT Size;
} NDIS_OBJECT_HEADER, *PNDIS_OBJECT_HEADER;
````


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


