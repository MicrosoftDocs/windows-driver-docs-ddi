---
UID: NS:ks.__unnamed_struct_25
title: KSNODE_CREATE (ks.h)
description: The KSNODE_CREATE structure describes the set of information used to create the node handle.
old-location: stream\ksnode_create.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KSNODE_CREATE structure"]
ms.keywords: "*PKSNODE_CREATE, KSNODE_CREATE, KSNODE_CREATE structure [Streaming Media Devices], PKSNODE_CREATE, PKSNODE_CREATE structure pointer [Streaming Media Devices], ks-struct_2fb3dcb7-5945-4f8a-b1f1-945910ec8396.xml, ks/KSNODE_CREATE, ks/PKSNODE_CREATE, stream.ksnode_create"
req.header: ks.h
req.include-header: Ks.h
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
req.typenames: KSNODE_CREATE, *PKSNODE_CREATE
f1_keywords:
 - PKSNODE_CREATE
 - ks/PKSNODE_CREATE
 - KSNODE_CREATE
 - ks/KSNODE_CREATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KSNODE_CREATE
---

# KSNODE_CREATE structure


## -description

The KSNODE_CREATE structure describes the set of information used to create the node handle.

## -struct-fields

### -field CreateFlags

Set to zero.

### -field Node

Indicates what node a handle should be created for. This refers to the node identifiers returned when querying topology information. A node identifier of −1 may be used to refer to the collection of nodes as a whole, if the filter supports it.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/nf-ks-kscreatetopologynode">KsCreateTopologyNode</a>
