---
UID: NF:wdm.IoRegisterDriverProxyEndpoints
tech.root: kernel
title: IoRegisterDriverProxyEndpoints
ms.date: 09/11/2025
targetos: Windows
description: Registers endpoint functions to a DriverProxy extension for hot-swappable functionality.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
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
 - IoRegisterDriverProxyEndpoints
f1_keywords:
 - IoRegisterDriverProxyEndpoints
 - wdm/IoRegisterDriverProxyEndpoints
dev_langs:
 - c++
helpviewer_keywords:
 - IoRegisterDriverProxyEndpoints
ai-usage: ai-assisted
---

## -description

> [!NOTE]
> This function is used for Driver Hot-Swap V1 only. New drivers should use Driver Hot-Swap V2, which handles endpoint registration automatically through compiler-based endpoint enumeration.

The **IoRegisterDriverProxyEndpoints** function registers endpoint functions to a DriverProxy extension, enabling hot-swappable driver functionality in Driver Hot-Swap V1 implementations.

## -parameters

### -param DriverProxyExtension

[in] A pointer to the DriverProxy extension that the endpoints will be registered to. This extension must have been created with [**IoCreateDriverProxyExtension**](nf-wdm-iocreatedriverproxyextension.md).

### -param EndpointInfo

[in, out] An array of [**DRIVER_PROXY_ENDPOINT_INFORMATION**](ns-wdm-driver_proxy_endpoint_information.md) structures that describe the endpoint functions to register. The function may modify the contents of this array during registration.

### -param Count

[in] The number of elements in the **EndpointInfo** array.

### -param PhasedCallback

[in, optional] An optional pointer to a [**DRIVER_PROXY_REGISTER_CALLBACK**](nc-wdm-driver_proxy_register_callback.md) function that will be called at various phases during the registration process to allow driver-specific operations.

### -param Context

[in, optional] An optional context pointer that will be passed to the **PhasedCallback** function.

## -returns

**IoRegisterDriverProxyEndpoints** returns one of the following NTSTATUS values:

| Return code | Description |
|-------------|-------------|
| **STATUS_SUCCESS** | The endpoints were successfully registered. |
| **STATUS_INSUFFICIENT_RESOURCES** | Insufficient memory was available to register the endpoints. |
| **STATUS_INVALID_PARAMETER_3** | One or more endpoint information structures attempted to overwrite an existing function with a different parameter count. |
| **STATUS_UNSUCCESSFUL** | The operation timed out while waiting for existing function calls to complete. |

## -remarks

This function establishes the mapping between original driver functions and their hot-swappable wrappers. Once registered, calls to the original functions will be redirected through the DriverProxy system, allowing the functions to be replaced at runtime without unloading the driver.

This function performs a complex multi-phase operation to safely replace function pointers while existing calls may be in progress. The registration process includes:

* Pre-processing phase: The optional **PhasedCallback** is called with **DriverProxyRegisterCallbackPreProcess** to allow driver preparation.

* Rundown acquisition: The function waits for all existing calls to registered endpoints to complete before proceeding.

* Proxy stalled phase: The **PhasedCallback** is called with **DriverProxyRegisterCallbackProxyStalled** while all calls are blocked.

* Function replacement: The actual function pointers are updated atomically.

* Post-processing phase: The **PhasedCallback** is called with **DriverProxyRegisterCallbackPostProcess** to allow driver cleanup.

If an endpoint has the same ID as an existing registered endpoint, the endpoint will be replaced, but only if it has the same parameter count.

This function serves dual purposes in Driver Hot-Swap V1: initial endpoint registration (where **PhasedCallback** should be NULL) and endpoint swapping during hot-swap operations.

The function must be called at PASSIVE_LEVEL as it may need to wait for existing function calls to complete.

## -see-also

[**IoCreateDriverProxyExtension**](nf-wdm-iocreatedriverproxyextension.md)

[**DRIVER_PROXY_ENDPOINT_INFORMATION**](ns-wdm-driver_proxy_endpoint_information.md)

[**DRIVER_PROXY_REGISTER_CALLBACK**](nc-wdm-driver_proxy_register_callback.md)

[**IoGetDriverProxyWrapperFromEndpoint**](nf-wdm-iogetdriverproxywrapperfromendpoint.md)
