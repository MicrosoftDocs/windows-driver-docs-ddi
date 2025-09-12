---
UID: NF:wdm.IoGetDriverProxyEndpointWrapper
tech.root: kernel
title: IoGetDriverProxyEndpointWrapper
ms.date: 09/05/2025
targetos: Windows
description: Gets the wrapper for an endpoint function by function ID. This function is deprecated.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: Any level
req.kmdf-ver: 
req.lib: NtosKrnl.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: Universal
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - NtosKrnl.exe
api_name:
 - IoGetDriverProxyEndpointWrapper
f1_keywords:
 - IoGetDriverProxyEndpointWrapper
 - wdm/IoGetDriverProxyEndpointWrapper
dev_langs:
 - c++
helpviewer_keywords:
 - IoGetDriverProxyEndpointWrapper
ai-usage: ai-assisted
---

## -description

> [!WARNING]
> **IoGetDriverProxyEndpointWrapper** is only available in Driver Hot-Swap V1 and is not supported in Driver Hot-Swap V2. New drivers should use Driver Hot-Swap V2 with [**IoGetDriverProxyWrapperFromEndpoint**](nf-wdm-iogetdriverproxywrapperfromendpoint.md) instead.

The **IoGetDriverProxyEndpointWrapper** function gets the pointer to the wrapper for an endpoint function using a function ID in Driver Hot-Swap V1 implementations.

## -parameters

### -param DriverProxyExtension

[in] A pointer to the DriverProxy extension that contains the registered endpoints.

### -param FunctionId

[in] The function ID of the endpoint function to search for. This is a deprecated mechanism for identifying endpoint functions.

## -returns

**IoGetDriverProxyEndpointWrapper** returns a pointer to the endpoint wrapper function, or NULL if the specified function ID could not be found.

## -remarks

This function is only available in Driver Hot-Swap V1 and is not supported in Driver Hot-Swap V2. New drivers should use Driver Hot-Swap V2 with [**IoGetDriverProxyWrapperFromEndpoint**](nf-wdm-iogetdriverproxywrapperfromendpoint.md) instead.

The function ID approach was used in the original Driver Hot-Swap implementation but is not part of the current Driver Hot-Swap V2 system.

## -see-also

[**IoGetDriverProxyWrapperFromEndpoint**](nf-wdm-iogetdriverproxywrapperfromendpoint.md)

[**IoRegisterDriverProxyEndpoints**](nf-wdm-ioregisterdriverproxyendpoints.md)
