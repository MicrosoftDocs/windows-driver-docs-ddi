---
UID: NS:pktmonnetevtnpik._PKTMON_NETEVT_CLIENT_DISPATCH_V2
tech.root: netvista
title: PKTMON_NETEVT_CLIENT_DISPATCH_V2
ms.date: 11/13/2025
targetos: Windows
description: Defines version 2 of the Packet Monitor NetEvt NMR client dispatch table, containing callback functions for the client module.
ai-usage: ai-assisted
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: pktmonnetevtnpik.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: PKTMON_NETEVT_CLIENT_DISPATCH_V2
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - pktmonnetevtnpik.h
api_name:
 - _PKTMON_NETEVT_CLIENT_DISPATCH_V2
 - PKTMON_NETEVT_CLIENT_DISPATCH_V2
f1_keywords:
 - _PKTMON_NETEVT_CLIENT_DISPATCH_V2
 - pktmonnetevtnpik/_PKTMON_NETEVT_CLIENT_DISPATCH_V2
 - PKTMON_NETEVT_CLIENT_DISPATCH_V2
 - pktmonnetevtnpik/PKTMON_NETEVT_CLIENT_DISPATCH_V2
dev_langs:
 - c++
helpviewer_keywords:
 - _PKTMON_NETEVT_CLIENT_DISPATCH_V2
---

## -description

The **PKTMON_NETEVT_CLIENT_DISPATCH_V2** structure represents version 2 of the Packet Monitor NetEvt NMR client dispatch table, containing callback functions for the client module. This structure extends the original dispatch table by adding capture type information to control which packet events (flow, drop, or both) are monitored.

## -struct-fields

### -field Header

A **[PKTMON_HEADER](../pktmonnpik/ns-pktmonnpik-pktmon_header.md)** structure containing version and size information for this dispatch table. The *Header* field enables version control and ensures proper structure alignment between client and provider modules.

### -field CaptureType

A **[PKTMON_CAPTURE_TYPE](../pktmondefk/ne-pktmondefk-pktmon_capture_type.md)** value specifying the type of packets to capture. This field determines whether the client monitors all packets, only flow packets, only dropped packets, or no packets at all.

### -field HandlerCount

The number of callback handler functions in the *Handlers* array. This count specifies how many event handler functions the client provides for processing packet events.

### -field Handlers

Pointer to an array of handler functions that the client provides for processing packet monitoring events. These callback functions are invoked by the provider when relevant packet events occur.

## -remarks

The client module must ensure this structure remains valid and resident in memory as long as the provider module is attached. A pointer to this structure is typically passed through the *ClientDispatch* parameter when calling **[NmrClientAttachProvider](/windows-hardware/drivers/ddi/netioddk/nf-netioddk-nmrclientattachprovider)**. Version 2 differs from the original **[PKTMON_NETEVT_CLIENT_DISPATCH](ns-pktmonnetevtnpik-pktmon_netevt_client_dispatch.md)** by including the *CaptureType* field to provide more granular control over which packet events are monitored.

## -see-also

- [PKTMON_HEADER](../pktmonnpik/ns-pktmonnpik-pktmon_header.md)
- [PKTMON_CAPTURE_TYPE](../pktmondefk/ne-pktmondefk-pktmon_capture_type.md)
- [PKTMON_NETEVT_CLIENT_DISPATCH](ns-pktmonnetevtnpik-pktmon_netevt_client_dispatch.md)

