---
UID: NC:pktmonclntnpik.PKTMON_PROVIDER_REGISTER_COMPONENT
tech.root: netvista
title: PKTMON_PROVIDER_REGISTER_COMPONENT
ms.date: 11/12/2025
targetos: Windows
description: The PKTMON_PROVIDER_REGISTER_COMPONENT callback function is invoked by the PktMonClnt application to register a new monitoring component.
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
 - PKTMON_PROVIDER_REGISTER_COMPONENT
f1_keywords:
 - PKTMON_PROVIDER_REGISTER_COMPONENT
 - pktmonclntnpik/PKTMON_PROVIDER_REGISTER_COMPONENT
dev_langs:
 - c++
helpviewer_keywords:
 - PKTMON_PROVIDER_REGISTER_COMPONENT
---

## -description

The **PKTMON_PROVIDER_REGISTER_COMPONENT** callback function is invoked by the PktMonClnt application to register a new monitoring component. This callback is part of the provider dispatch table and is called when a client needs to register a component with the packet monitoring infrastructure.

## -parameters

### -param ProviderBindingContext

An opaque context pointer representing the provider binding. This context was established during the provider-client attachment and is used to identify the specific provider instance handling this operation.

### -param Component

A pointer to a **[PKTMON_COMPONENT_IN](ns-pktmonclntnpik-pktmon_component_in.md)** structure containing the component registration information, including the component's name, description, type, and packet type it will monitor.

### -param CompHandle

A pointer to a handle that receives the component handle upon successful registration. This handle is used in subsequent operations involving this component.

## -returns

Returns `STATUS_SUCCESS` if the component registration succeeds. Otherwise, returns an appropriate `NTSTATUS` error code indicating the failure reason.

## -remarks

This callback is part of the **[PKTMON_PROVIDER_DISPATCH](ns-pktmonclntnpik-pktmon_provider_dispatch.md)** structure and is invoked by the PktMonClnt application. The provider implementation should validate the component information and allocate necessary resources for tracking this component.

## -see-also

- [PKTMON_COMPONENT_IN](ns-pktmonclntnpik-pktmon_component_in.md)
- [PKTMON_PROVIDER_DISPATCH](ns-pktmonclntnpik-pktmon_provider_dispatch.md)
- [PktMonClntComponentRegister](../pktmonclntk/nf-pktmonclntk-pktmonclntcomponentregister.md)

