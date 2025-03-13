---
UID: NS:pktmonnpik._PKTMON_NETEVT_CLIENT_DISPATCH
tech.root: netvista
title: PKTMON_NETEVT_CLIENT_DISPATCH
ms.date: 03/13/2025
targetos: Windows
description: The PKTMON_NETEVT_CLIENT_DISPATCH structure contains a Packet Monitor NetEvt NMR client dispatch table.
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
req.typenames: PKTMON_NETEVT_CLIENT_DISPATCH
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
 - _PKTMON_NETEVT_CLIENT_DISPATCH
 - PKTMON_NETEVT_CLIENT_DISPATCH
f1_keywords:
 - _PKTMON_NETEVT_CLIENT_DISPATCH
 - pktmonnpik/_PKTMON_NETEVT_CLIENT_DISPATCH
 - PKTMON_NETEVT_CLIENT_DISPATCH
 - pktmonnpik/PKTMON_NETEVT_CLIENT_DISPATCH
dev_langs:
 - c++
helpviewer_keywords:
 - _PKTMON_NETEVT_CLIENT_DISPATCH
---

## -description

The **PKTMON_NETEVT_CLIENT_DISPATCH** structure contains a Packet Monitor NetEvt NMR client dispatch table.

The **PKTMON_NETEVT_CLIENT_DISPATCH** structure contains the Packet Monitor NetEvt NMR client dispatch table of [NPI](/windows-hardware/drivers/network/network-programming-interface) callback functions for the client module. A pointer to this structure is passed through the *ClientDispatch* parameter when calling **[NmrClientAttachProvider](../netioddk/nf-netioddk-nmrclientattachprovider.md)**.

## -struct-fields

### -field Header

Represents header information as described in **[PKTMON_NETEVT_DISPATCH_HEADER](ns-pktmonnpik-pktmon_netevt_dispatch_header.md)**.

### -field HandlerCount

The number of handler functions.

### -field Handlers

Pointer to the list of hanlder functions.

## -remarks

The client module must make sure that this structure remains valid and resident in memory as long as the provider module is attached to the client module. The contents of the structure are NPI-specific.

## -see-also

- [NPI](/windows-hardware/drivers/network/network-programming-interface)
- **[NmrClientAttachProvider](../netioddk/nf-netioddk-nmrclientattachprovider.md)**
- **[PKTMON_NETEVT_DISPATCH_HEADER](ns-pktmonnpik-pktmon_netevt_dispatch_header.md)**
