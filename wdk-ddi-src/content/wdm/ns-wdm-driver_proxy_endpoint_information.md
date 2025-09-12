---
UID: NS:wdm._DRIVER_PROXY_ENDPOINT_INFORMATION
tech.root: kernel
title: DRIVER_PROXY_ENDPOINT_INFORMATION
ms.date: 09/11/2025
targetos: Windows
description: Contains information about a DriverProxy endpoint function for registration with the hot-swap system.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: Universal
req.typenames: DRIVER_PROXY_ENDPOINT_INFORMATION, *PDRIVER_PROXY_ENDPOINT_INFORMATION
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _DRIVER_PROXY_ENDPOINT_INFORMATION
 - PDRIVER_PROXY_ENDPOINT_INFORMATION
 - DRIVER_PROXY_ENDPOINT_INFORMATION
f1_keywords:
 - _DRIVER_PROXY_ENDPOINT_INFORMATION
 - wdm/_DRIVER_PROXY_ENDPOINT_INFORMATION
 - PDRIVER_PROXY_ENDPOINT_INFORMATION
 - wdm/PDRIVER_PROXY_ENDPOINT_INFORMATION
 - DRIVER_PROXY_ENDPOINT_INFORMATION
 - wdm/DRIVER_PROXY_ENDPOINT_INFORMATION
dev_langs:
 - c++
helpviewer_keywords:
 - _DRIVER_PROXY_ENDPOINT_INFORMATION
ai-usage: ai-generated
---

## -description

> [!NOTE]
> This structure is used for Driver Hot-Swap V1 only. New drivers should use Driver Hot-Swap V2, which handles endpoint registration automatically through compiler-based endpoint enumeration.

The **DRIVER_PROXY_ENDPOINT_INFORMATION** structure contains information about a DriverProxy endpoint function that is being registered for hot-swappable functionality in Driver Hot-Swap V1 implementations.

## -struct-fields

### -field Id

A unique identifier for the endpoint function. This ID is used to identify the endpoint within the DriverProxy system and must be unique within the scope of the DriverProxy extension. If an endpoint with the same ID already exists, it will be replaced during registration, provided the parameter count matches.

### -field EndpointFunction

A pointer to the [**DRIVER_PROXY_ENDPOINT_FUNCTION**](nc-wdm-driver_proxy_endpoint_function.md) that represents the endpoint function to be registered. This is the actual function that will be made hot-swappable through the DriverProxy system.

### -field ParameterCount

The number of parameters that the endpoint function accepts. This value is used for validation during endpoint registration. If an endpoint with the same ID already exists, the parameter count must match exactly, or the registration will fail with **STATUS_INVALID_PARAMETER_3**.

## -remarks

This structure is used with [**IoRegisterDriverProxyEndpoints**](nf-wdm-ioregisterdriverproxyendpoints.md) to register endpoint functions in Driver Hot-Swap V1 implementations, which require manual registration. Each structure in the array describes one endpoint function that should be made hot-swappable.

Driver Hot-Swap V2 automatically discovers and registers endpoints during the build process, eliminating the need for this structure in newer implementations.

When registering multiple endpoints, all endpoints in the array are processed atomically. Either all endpoints are successfully registered, or the entire operation fails and no changes are made.

## -see-also

[**IoRegisterDriverProxyEndpoints**](nf-wdm-ioregisterdriverproxyendpoints.md)

[**DRIVER_PROXY_ENDPOINT_FUNCTION**](nc-wdm-driver_proxy_endpoint_function.md)

[**DRIVER_PROXY_REGISTER_CALLBACK**](nc-wdm-driver_proxy_register_callback.md)

[**IoCreateDriverProxyExtension**](nf-wdm-iocreatedriverproxyextension.md)

[**IoGetDriverProxyEndpointWrapper**](nf-wdm-iogetdriverproxyendpointwrapper.md)
