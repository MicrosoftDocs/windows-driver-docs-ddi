---
UID: NC:pktmonclntnpik.PKTMON_PROVIDER_UNREGISTER_COMPONENT
tech.root: netvista
title: PKTMON_PROVIDER_UNREGISTER_COMPONENT
ms.date: 11/12/2025
targetos: Windows
description: The PKTMON_PROVIDER_UNREGISTER_COMPONENT callback function is invoked by the Packet Monitor provider to unregister a monitoring component and free its resources.
prerelease: true
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
 - PKTMON_PROVIDER_UNREGISTER_COMPONENT
f1_keywords:
 - PKTMON_PROVIDER_UNREGISTER_COMPONENT
 - pktmonclntnpik/PKTMON_PROVIDER_UNREGISTER_COMPONENT
dev_langs:
 - c++
helpviewer_keywords:
 - PKTMON_PROVIDER_UNREGISTER_COMPONENT
---

## -description

The **PKTMON_PROVIDER_UNREGISTER_COMPONENT** callback function is invoked by the Packet Monitor provider to unregister a monitoring component and free its resources. This callback is called when a component is no longer needed for packet monitoring.

## -parameters

### -param ProviderBindingContext

An opaque context pointer representing the provider binding. This context identifies the specific provider instance handling this operation.

### -param CompHandle

A handle to the component being unregistered. This handle was returned from a previous **[PKTMON_PROVIDER_REGISTER_COMPONENT](nc-pktmonclntnpik-pktmon_provider_register_component.md)** callback invocation.

## -remarks

This callback is part of the **[PKTMON_PROVIDER_DISPATCH](ns-pktmonclntnpik-pktmon_provider_dispatch.md)** structure and is invoked when a client calls **[PktMonClntComponentUnregister](../pktmonclntk/nf-pktmonclntk-pktmonclntcomponentunregister.md)**. The provider should release all resources associated with this component, including any edges that were added to it.

## -see-also

- [PKTMON_PROVIDER_REGISTER_COMPONENT](nc-pktmonclntnpik-pktmon_provider_register_component.md)
- [PKTMON_PROVIDER_DISPATCH](ns-pktmonclntnpik-pktmon_provider_dispatch.md)
- [PktMonClntComponentUnregister](../pktmonclntk/nf-pktmonclntk-pktmonclntcomponentunregister.md)

