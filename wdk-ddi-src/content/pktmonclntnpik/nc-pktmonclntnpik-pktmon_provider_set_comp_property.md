---
UID: NC:pktmonclntnpik.PKTMON_PROVIDER_SET_COMP_PROPERTY
tech.root: netvista
title: PKTMON_PROVIDER_SET_COMP_PROPERTY
ms.date: 11/12/2025
targetos: Windows
description: The PKTMON_PROVIDER_SET_COMP_PROPERTY callback function is invoked by the PktMonClnt application to set a property on a registered component.
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
 - PKTMON_PROVIDER_SET_COMP_PROPERTY
f1_keywords:
 - PKTMON_PROVIDER_SET_COMP_PROPERTY
 - pktmonclntnpik/PKTMON_PROVIDER_SET_COMP_PROPERTY
dev_langs:
 - c++
helpviewer_keywords:
 - PKTMON_PROVIDER_SET_COMP_PROPERTY
---

## -description

The **PKTMON_PROVIDER_SET_COMP_PROPERTY** callback function is invoked by the PktMonClnt application to set a property on a registered component. This callback allows dynamic configuration of component behavior through property updates.

## -parameters

### -param ProviderBindingContext

An opaque context pointer representing the provider binding. This context identifies the specific provider instance handling this operation.

### -param CompHandle

A handle to the component whose property is being set. This handle was returned from a previous **[PKTMON_PROVIDER_REGISTER_COMPONENT](nc-pktmonclntnpik-pktmon_provider_register_component.md)** callback invocation.

### -param Property

A pointer to a **[PKTMON_COMP_PROPERTY_IN](ns-pktmonclntnpik-pktmon_comp_property_in.md)** structure containing the property identifier, value, and size information.

## -returns

Returns `STATUS_SUCCESS` if the property is successfully set. Otherwise, returns an appropriate `NTSTATUS` error code indicating the failure reason.

## -remarks

This callback is part of the **[PKTMON_PROVIDER_DISPATCH](ns-pktmonclntnpik-pktmon_provider_dispatch.md)** structure and is invoked by the PktMonClnt application.

## -see-also

- [PKTMON_COMP_PROPERTY_IN](ns-pktmonclntnpik-pktmon_comp_property_in.md)
- [PKTMON_PROVIDER_DISPATCH](ns-pktmonclntnpik-pktmon_provider_dispatch.md)
- [PktMonClntSetComponentProperty](../pktmonclntk/nf-pktmonclntk-pktmonclntsetcomponentproperty.md)

