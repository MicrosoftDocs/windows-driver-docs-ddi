---
UID: NC:pktmonclntnpik.PKTMON_PROVIDER_ADD_EDGE
tech.root: netvista
title: PKTMON_PROVIDER_ADD_EDGE
ms.date: 11/12/2025
targetos: Windows
description: The PKTMON_PROVIDER_ADD_EDGE callback function is invoked by the PktMonClnt application to add an edge to a registered component
ai-usage: ai-assisted
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: pktmonclntnpik.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - Callback
api_location:
 - pktmonclntnpik.h
api_name:
 - PKTMON_PROVIDER_ADD_EDGE
f1_keywords:
 - PKTMON_PROVIDER_ADD_EDGE
 - pktmonclntnpik/PKTMON_PROVIDER_ADD_EDGE
dev_langs:
 - c++
helpviewer_keywords:
 - PKTMON_PROVIDER_ADD_EDGE
---

## -description

The **PKTMON_PROVIDER_ADD_EDGE** callback function is invoked by the PktMonClnt application to add an edge to a registered component. An edge represents a packet monitoring boundary (entry/exit point) where packets flow through the component, allowing the component to report packet events at specific boundaries.

## -parameters

### -param ProviderBindingContext

An opaque context pointer representing the provider binding. This context identifies the specific provider instance handling this operation.

### -param CompHandle

A handle to the component to which the edge will be added. This handle was returned from a previous **[PKTMON_PROVIDER_REGISTER_COMPONENT](nc-pktmonclntnpik-pktmon_provider_register_component.md)** callback invocation.

### -param Edge

A pointer to a **[PKTMON_EDGE_IN](ns-pktmonclntnpik-pktmon_edge_in.md)** structure containing information about the edge being added, including its name and packet type.

### -param EdgeHandle

A pointer to a handle that receives the edge handle upon successful addition. This handle is used when logging or reporting packet events at this edge.

## -returns

Returns `STATUS_SUCCESS` if the edge is successfully added. Otherwise, returns an appropriate `NTSTATUS` error code indicating the failure reason.

## -remarks

This callback is part of the **[PKTMON_PROVIDER_DISPATCH](ns-pktmonclntnpik-pktmon_provider_dispatch.md)** structure and is invoked by the PktMonClnt application. Components can have multiple edges representing different monitoring points.

## -see-also

- [PKTMON_EDGE_IN](ns-pktmonclntnpik-pktmon_edge_in.md)
- [PKTMON_PROVIDER_DISPATCH](ns-pktmonclntnpik-pktmon_provider_dispatch.md)
- [PktMonClntAddEdge](../pktmonclntk/nf-pktmonclntk-pktmonclntaddedge.md)

