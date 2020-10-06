---
UID: NS:ks._KSNODE_DESCRIPTOR
title: _KSNODE_DESCRIPTOR (ks.h)
description: The KSNODE_DESCRIPTOR structure describes a topology node within a filter.
old-location: stream\ksnode_descriptor.htm
tech.root: stream
ms.assetid: dfc5760f-fdd6-45f3-aeac-4406892e518a
ms.date: 04/23/2018
keywords: ["KSNODE_DESCRIPTOR structure"]
ms.keywords: "*PKSNODE_DESCRIPTOR, KSNODE_DESCRIPTOR, KSNODE_DESCRIPTOR structure [Streaming Media Devices], PKSNODE_DESCRIPTOR, PKSNODE_DESCRIPTOR structure pointer [Streaming Media Devices], _KSNODE_DESCRIPTOR, avstruct_c4e79318-e112-4f57-ad6f-58e71ec53532.xml, ks/KSNODE_DESCRIPTOR, ks/PKSNODE_DESCRIPTOR, stream.ksnode_descriptor"
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: Available in Microsoft Windows XP and later operating systems and in Microsoft DirectX 8.0 and later versions.
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
req.typenames: KSNODE_DESCRIPTOR, *PKSNODE_DESCRIPTOR
f1_keywords:
 - _KSNODE_DESCRIPTOR
 - ks/_KSNODE_DESCRIPTOR
 - PKSNODE_DESCRIPTOR
 - ks/PKSNODE_DESCRIPTOR
 - KSNODE_DESCRIPTOR
 - ks/KSNODE_DESCRIPTOR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KSNODE_DESCRIPTOR
---

# _KSNODE_DESCRIPTOR structure


## -description

The KSNODE_DESCRIPTOR structure describes a topology node within a filter.

## -struct-fields

### -field AutomationTable

A pointer to a <a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksautomation_table_">KSAUTOMATION_TABLE</a> structure for this topology node. The automation table contains the properties, methods, and events supported by this topology node.

### -field Type

A pointer to a GUID defining the topology node.

### -field Name

A pointer to a GUID that represents the name of this topology node. This is used to return information about a <a href="/windows-hardware/drivers/stream/ksproperty-topology-name">KSPROPERTY_TOPOLOGY_NAME</a> query.

### -field Alignment

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-_ksfilter_descriptor">KSFILTER_DESCRIPTOR</a>