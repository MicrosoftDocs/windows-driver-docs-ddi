---
UID: NC:pktmonclntnpik.PKTMON_PROVIDER_PACKET_LOG
tech.root: netvista
title: PKTMON_PROVIDER_PACKET_LOG
ms.date: 11/2/2025
targetos: Windows
description: The PKTMON_PROVIDER_PACKET_LOG callback function is invoked by the PktMonClnt application to log packet flow events.
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
 - LibDef
api_location:
 - pktmonclntnpik.h
api_name:
 - PKTMON_PROVIDER_PACKET_LOG
f1_keywords:
 - PKTMON_PROVIDER_PACKET_LOG
 - pktmonclntnpik/PKTMON_PROVIDER_PACKET_LOG
dev_langs:
 - c++
helpviewer_keywords:
 - PKTMON_PROVIDER_PACKET_LOG
---

## -description

The **PKTMON_PROVIDER_PACKET_LOG** callback function is invoked by the PktMonClnt application to log packet flow events. This callback is called when a packet successfully flows through a monitored component edge, as opposed to being dropped.

## -parameters

### -param ProviderBindingContext

An opaque context pointer representing the provider binding. This context identifies the specific provider instance handling this packet logging operation.

### -param EdgeHandle

A handle to the edge where the packet flow event occurred. This handle was returned from a previous **[PKTMON_PROVIDER_ADD_EDGE](nc-pktmonclntnpik-pktmon_provider_add_edge.md)** callback invocation.

### -param PacketLog

A pointer to a **[PKTMON_PACKET_LOG_IN](ns-pktmonclntnpik-pktmon_packet_log_in.md)** structure containing information about the packet being logged, including direction, packet type, and optional header information.

### -param Context

An optional pointer to a **[PKTMON_PACKET_CONTEXT_IN](ns-pktmonclntnpik-pktmon_packet_context_in.md)** structure containing component-specific context information, such as a connection ID. Can be NULL.

## -remarks

This callback is part of the **[PKTMON_PROVIDER_DISPATCH](ns-pktmonclntnpik-pktmon_provider_dispatch.md)** structure and is invoked by the PktMonClnt application to report that a packet successfully flowed through a monitoring point.

## -see-also

- [PKTMON_PACKET_LOG_IN](ns-pktmonclntnpik-pktmon_packet_log_in.md)
- [PKTMON_PACKET_CONTEXT_IN](ns-pktmonclntnpik-pktmon_packet_context_in.md)
- [PKTMON_PROVIDER_DISPATCH](ns-pktmonclntnpik-pktmon_provider_dispatch.md)
- [PktMonClntNblLog](../pktmonclntk/nf-pktmonclntk-pktmonclntnbllog.md)
- [PktMonClntHeaderInfoLog](../pktmonclntk/nf-pktmonclntk-pktmonclntheaderinfolog.md)

