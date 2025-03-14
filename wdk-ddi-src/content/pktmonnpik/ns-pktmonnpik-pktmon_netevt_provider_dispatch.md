---
UID: NS:pktmonnpik._PKTMON_NETEVT_PROVIDER_DISPATCH
tech.root: netvista
title: PKTMON_NETEVT_PROVIDER_DISPATCH
ms.date: 03/14/2025
targetos: Windows
description: The PKTMON_NETEVT_PROVIDER_DISPATCH structure contains a Packet Monitor NMR provider dispatch table.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: pktmonnpik.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: PKTMON_NETEVT_PROVIDER_DISPATCH
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - pktmonnpik.h
api_name:
 - _PKTMON_NETEVT_PROVIDER_DISPATCH
 - PKTMON_NETEVT_PROVIDER_DISPATCH
f1_keywords:
 - _PKTMON_NETEVT_PROVIDER_DISPATCH
 - pktmonnpik/_PKTMON_NETEVT_PROVIDER_DISPATCH
 - PKTMON_NETEVT_PROVIDER_DISPATCH
 - pktmonnpik/PKTMON_NETEVT_PROVIDER_DISPATCH
dev_langs:
 - c
 - c++
helpviewer_keywords:
 - _PKTMON_NETEVT_PROVIDER_DISPATCH
---

## -description

The **PKTMON_NETEVT_PROVIDER_DISPATCH** structure contains a Packet Monitor NMR provider dispatch table.

## -struct-fields

### -field Header

The [PKTMON_NETEVT_DISPATCH_HEADER](ns-pktmonnpik-pktmon_netevt_dispatch_header.md) structure for this dispatch table.

### -field HandlerCount

The number of event handlers.

### -field Handlers

Pointer to the event handlers.

## -remarks

## -see-also

- [PKTMON_NETEVT_DISPATCH_HEADER](ns-pktmonnpik-pktmon_netevt_dispatch_header.md)
