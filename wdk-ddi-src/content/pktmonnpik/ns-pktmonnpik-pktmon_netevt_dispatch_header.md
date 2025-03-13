---
UID: NS:pktmonnpik._PKTMON_NETEVT_DISPATCH_HEADER
tech.root: netvista
title: PKTMON_NETEVT_DISPATCH_HEADER
ms.date: 03/13/2025
targetos: Windows
description: The PKTMON_NETEVT_DISPATCH_HEADER structure contains the header for a PKTMON_NETEVT_PROVIDER_DISPATCH structure
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
req.typenames: PKTMON_NETEVT_DISPATCH_HEADER
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
 - _PKTMON_NETEVT_DISPATCH_HEADER
 - PKTMON_NETEVT_DISPATCH_HEADER
f1_keywords:
 - _PKTMON_NETEVT_DISPATCH_HEADER
 - pktmonnpik/_PKTMON_NETEVT_DISPATCH_HEADER
 - PKTMON_NETEVT_DISPATCH_HEADER
 - pktmonnpik/PKTMON_NETEVT_DISPATCH_HEADER
dev_langs:
 - c++
helpviewer_keywords:
 - _PKTMON_NETEVT_DISPATCH_HEADER
---

## -description

The **PKTMON_NETEVT_DISPATCH_HEADER** structure contains the header for a **[PKTMON_NETEVT_PROVIDER_DISPATCH](ns-pktmonnpik-pktmon_netevt_provider_dispatch.md)** structure.

## -struct-fields

### -field Version

The version of the PktMon programming interface that the application would like to use. Currently, only version 1 is supported.

### -field Size

The size of the **[PKTMON_NETEVT_CLIENT_DISPATCH](ns-pktmonnpik-pktmon_netevt_client_dispatch.md)** structure.

## -remarks

## -see-also

- **[PKTMON_NETEVT_PROVIDER_DISPATCH](ns-pktmonnpik-pktmon_netevt_provider_dispatch.md)**
- **[PKTMON_NETEVT_CLIENT_DISPATCH](ns-pktmonnpik-pktmon_netevt_client_dispatch.md)**
