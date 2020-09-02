---
UID: NS:ks.__unnamed_struct_5
title: KSE_NODE (ks.h)
description: The KSE_NODE structure specifies an event request on a specific node.
old-location: stream\kse_node.htm
tech.root: stream
ms.assetid: 89446165-cdc3-414d-bcce-f2c978d94547
ms.date: 04/23/2018
keywords: ["KSE_NODE structure"]
ms.keywords: "*PKSE_NODE, KSE_NODE, KSE_NODE structure [Streaming Media Devices], PKSE_NODE, PKSE_NODE structure pointer [Streaming Media Devices], ks-struct_701a51ab-90d7-47d6-8e40-bd30d0ddd7b9.xml, ks/KSE_NODE, ks/PKSE_NODE, stream.kse_node"
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
req.typenames: KSE_NODE, *PKSE_NODE
f1_keywords:
 - PKSE_NODE
 - ks/PKSE_NODE
 - KSE_NODE
 - ks/KSE_NODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ks.h
api_name:
 - KSE_NODE
---

# KSE_NODE structure


## -description

The KSE_NODE structure specifies an event request on a specific node.

## -struct-fields

### -field Event

A structure of type <a href="https://docs.microsoft.com/previous-versions/ff561744(v=vs.85)">KSEVENT</a> that identifies the requested event.

### -field NodeId

Specifies the node ID.

### -field Reserved

Reserved for system use. Should be set to zero.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ks/ns-ks-ksp_node">KSP_NODE</a>

