---
UID: NS:bdamedia.__unnamed_struct_0
title: KSP_NODE_ESPID (bdamedia.h)
description: The KSP_NODE_ESPID structure describes property and node type for an Entitlement Control Message (ECM) map node along with the packet identifier (PID) for an elementary stream that the ECM map node processes.
old-location: stream\ksp_node_espid.htm
tech.root: stream
ms.date: 04/23/2018
keywords: ["KSP_NODE_ESPID structure"]
ms.keywords: "*PKSP_NODE_ESPID, KSP_NODE_ESPID, KSP_NODE_ESPID structure [Streaming Media Devices], PKSP_NODE_ESPID, PKSP_NODE_ESPID structure pointer [Streaming Media Devices], bdamedia/KSP_NODE_ESPID, bdamedia/PKSP_NODE_ESPID, bdaref_aef92a8d-df0e-4283-b06a-4ece33b91809.xml, stream.ksp_node_espid"
req.header: bdamedia.h
req.include-header: Bdamedia.h
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
req.typenames: KSP_NODE_ESPID, *PKSP_NODE_ESPID
f1_keywords:
 - PKSP_NODE_ESPID
 - bdamedia/PKSP_NODE_ESPID
 - KSP_NODE_ESPID
 - bdamedia/KSP_NODE_ESPID
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - bdamedia.h
api_name:
 - KSP_NODE_ESPID
---

# KSP_NODE_ESPID structure


## -description

The KSP_NODE_ESPID structure describes property and node type for an Entitlement Control Message (ECM) map node along with the packet identifier (PID) for an elementary stream that the ECM map node processes.

## -struct-fields

### -field Property

KSP_NODE structure that describes a property and node type.

### -field EsPid

Packet identifier (PID) that identifies packets in the elementary stream.

## -see-also

<a href="/windows-hardware/drivers/ddi/ks/ns-ks-ksp_node">KSP_NODE</a>
