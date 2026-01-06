---
UID: NC:pktmonclntnpik.PKTMON_PROVIDER_PACKET_DROP
tech.root: netvista        
title: PKTMON_PROVIDER_PACKET_DROP
ms.date: 11/12/2025
targetos: Windows
description: The PKTMON_PROVIDER_PACKET_DROP callback function is invoked by the PktMonClnt application to log packet drop events.
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
 - PKTMON_PROVIDER_PACKET_DROP
f1_keywords:
 - PKTMON_PROVIDER_PACKET_DROP
 - pktmonclntnpik/PKTMON_PROVIDER_PACKET_DROP
dev_langs:
 - c++
helpviewer_keywords:
 - PKTMON_PROVIDER_PACKET_DROP
---

## -description

The **PKTMON_PROVIDER_PACKET_DROP** callback function is invoked by the PktMonClnt application to log packet drop events. This callback is called when a packet is dropped by a monitored component, recording the drop reason and location for diagnostic purposes.

## -parameters

### -param ProviderBindingContext

An opaque context pointer representing the provider binding. This context identifies the specific provider instance handling this packet drop logging operation.

### -param CompHandle

A handle to the component where the packet drop occurred. This handle was returned from a previous **[PKTMON_PROVIDER_REGISTER_COMPONENT](nc-pktmonclntnpik-pktmon_provider_register_component.md)** callback invocation.

### -param PacketLog

A pointer to a **[PKTMON_PACKET_LOG_IN](ns-pktmonclntnpik-pktmon_packet_log_in.md)** structure containing information about the dropped packet, including direction, packet type, and optional header information.

### -param DropReport

A pointer to a **[PKTMON_DROP_REPORT_IN](ns-pktmonclntnpik-pktmon_drop_report_in.md)** structure containing the drop reason code and drop location code that explain why and where the packet was dropped.

### -param Context

An optional pointer to a **[PKTMON_PACKET_CONTEXT_IN](ns-pktmonclntnpik-pktmon_packet_context_in.md)** structure containing component-specific context information. Can be NULL.

## -remarks

This callback is part of the **[PKTMON_PROVIDER_DISPATCH](ns-pktmonclntnpik-pktmon_provider_dispatch.md)** structure and is invoked by the PktMonClnt application to report that a packet was dropped.

## -see-also

- [PKTMON_PACKET_LOG_IN](ns-pktmonclntnpik-pktmon_packet_log_in.md)
- [PKTMON_DROP_REPORT_IN](ns-pktmonclntnpik-pktmon_drop_report_in.md)
- [PKTMON_PACKET_CONTEXT_IN](ns-pktmonclntnpik-pktmon_packet_context_in.md)
- [PKTMON_PROVIDER_DISPATCH](ns-pktmonclntnpik-pktmon_provider_dispatch.md)
- [PktMonClntNblDrop](../pktmonclntk/nf-pktmonclntk-pktmonclntnbldrop.md)
- [PktMonClntHeaderInfoDrop](../pktmonclntk/nf-pktmonclntk-pktmonclntheaderinfodrop.md)

