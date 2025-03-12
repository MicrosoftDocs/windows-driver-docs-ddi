---
UID: NS:pktmonnpik._PKTMON_NETEVT_CLIENT_CONTEXT
tech.root: netvista
title: PKTMON_NETEVT_CLIENT_CONTEXT
ms.date: 03/11/2025
targetos: Windows
description: The PKTMON_NETEVT_CLIENT_CONTEXT structure contains the client context for a net event.
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
req.typenames: PKTMON_NETEVT_CLIENT_CONTEXT
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
 - _PKTMON_NETEVT_CLIENT_CONTEXT
 - PKTMON_NETEVT_CLIENT_CONTEXT
f1_keywords:
 - _PKTMON_NETEVT_CLIENT_CONTEXT
 - pktmonnpik/_PKTMON_NETEVT_CLIENT_CONTEXT
 - PKTMON_NETEVT_CLIENT_CONTEXT
 - pktmonnpik/PKTMON_NETEVT_CLIENT_CONTEXT
dev_langs:
 - c++
helpviewer_keywords:
 - _PKTMON_NETEVT_CLIENT_CONTEXT
---

## -description

The **PKTMON_NETEVT_CLIENT_CONTEXT** structure contains the NMR client context for a net event.

## -struct-fields

### -field NmrClientHandle

A handle used by the NMR to represent the registration of the client module.

### -field RundownRef

Pointer to an opaque **EX_RUNDOWN_REF_CACHE_AWARE** structure.

### -field Enabled

### -field ProviderContext

### -field ProviderDispatch

## -remarks

## -see-also

