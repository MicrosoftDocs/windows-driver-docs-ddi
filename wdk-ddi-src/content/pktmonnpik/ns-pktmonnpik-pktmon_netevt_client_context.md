---
UID: NS:pktmonnpik._PKTMON_NETEVT_CLIENT_CONTEXT
tech.root: netvista
title: PKTMON_NETEVT_CLIENT_CONTEXT
ms.date: 03/13/2025
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

The **PKTMON_NETEVT_CLIENT_CONTEXT** structure represents the *ClientContext* to be passed to **[NmrRegisterClient](../netioddk/nf-netioddk-nmrregisterclient.md)** to register a network event client module using NMR.

## -struct-fields

### -field NmrClientHandle

A handle used by the NMR to represent the registration of the client module.

### -field RundownRef

Pointer to an opaque **EX_RUNDOWN_REF_CACHE_AWARE** structure.

### -field Enabled

### -field ProviderContext

Pointer to the provider context.

### -field ProviderDispatch

Pointer to a **[PKTMON_NETEVT_PROVIDER_DISPATCH](ns-pktmonnpik-pktmon_netevt_provider_dispatch.md)** provider dispatch structure.

## -remarks

The client module uses this context to keep track of the state of the client registration. The contents of the client module's registration context are opaque to the NMR. The NMR passes this pointer to the client module whenever it calls the client module's **[NPI_CLIENT_ATTACH_PROVIDER_FN](../netioddk/nc-netioddk-npi_client_attach_provider_fn.md)** callback function. The client module must make sure that its registration context remains valid and resident in memory as long as the client module is registered with the NMR.

## -see-also

- **[NmrRegisterClient](../netioddk/nf-netioddk-nmrregisterclient.md)**
- **[PKTMON_NETEVT_PROVIDER_DISPATCH](ns-pktmonnpik-pktmon_netevt_provider_dispatch.md)**
- **[NPI_CLIENT_ATTACH_PROVIDER_FN](../netioddk/nc-netioddk-npi_client_attach_provider_fn.md)**
