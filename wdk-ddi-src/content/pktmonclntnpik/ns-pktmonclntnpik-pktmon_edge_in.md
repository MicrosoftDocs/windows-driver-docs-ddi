---
UID: NS:pktmonclntnpik._PKTMON_EDGE_IN
tech.root: netvista
title: PKTMON_EDGE_IN
ms.date: 11/12/2025
targetos: Windows
description: The PKTMON_EDGE_IN structure contains information about a monitoring edge being added to a component.
ai-usage: ai-assisted
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: pktmonclntnpik.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: PKTMON_EDGE_IN
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - pktmonclntnpik.h
api_name:
 - _PKTMON_EDGE_IN
 - PKTMON_EDGE_IN
f1_keywords:
 - _PKTMON_EDGE_IN
 - pktmonclntnpik/_PKTMON_EDGE_IN
 - PKTMON_EDGE_IN
 - pktmonclntnpik/PKTMON_EDGE_IN
dev_langs:
 - c++
helpviewer_keywords:
 - _PKTMON_EDGE_IN
---

## -description

The **PKTMON_EDGE_IN** structure contains information about a monitoring edge being added to a component. An edge represents a packet monitoring boundary where packets can be tracked as they flow through the component.

## -struct-fields

### -field Header

A [PKTMON_HEADER](../pktmonnpik/ns-pktmonnpik-pktmon_header) structure used for versioning and size validation.

### -field Name

A Unicode string containing the name of the edge. This name is used for identification in packet logs and diagnostic output.

### -field DirTagIn

A Unicode string tag for inbound packet direction at this edge. This tag appears in packet logs to identify packets entering through this monitoring point.

### -field DirTagOut

A Unicode string tag for outbound packet direction at this edge. This tag appears in packet logs to identify packets leaving through this monitoring point.

## -remarks

This structure is passed to **[PKTMON_PROVIDER_ADD_EDGE](nc-pktmonclntnpik-pktmon_provider_add_edge.md)** when calling **[PktMonClntAddEdge](../pktmonclntk/nf-pktmonclntk-pktmonclntaddedge.md)** to define a new monitoring boundary within a component.

## -see-also

- [PKTMON_PROVIDER_ADD_EDGE](nc-pktmonclntnpik-pktmon_provider_add_edge.md)
- [PktMonClntAddEdge](../pktmonclntk/nf-pktmonclntk-pktmonclntaddedge.md)
- [PKTMON_EDGE_CONTEXT](../pktmonclntk/ns-pktmonclntk-pktmon_edge_context.md)

