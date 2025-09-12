---
UID: NF:wdm.IofGetDriverProxyWrapperFromEndpoint
tech.root: kernel
title: IofGetDriverProxyWrapperFromEndpoint
ms.date: 09/05/2025
targetos: Windows
description: Gets the wrapper for an endpoint function using the endpoint function pointer.
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
 - IofGetDriverProxyWrapperFromEndpoint
f1_keywords:
 - IofGetDriverProxyWrapperFromEndpoint
 - wdm/IofGetDriverProxyWrapperFromEndpoint
dev_langs:
 - c++
helpviewer_keywords:
 - IofGetDriverProxyWrapperFromEndpoint
ai-usage: ai-assisted
---

## -description

The **IofGetDriverProxyWrapperFromEndpoint** function gets the pointer to the wrapper for an endpoint function using the endpoint function pointer.

## -parameters

### -param DriverProxyExtension

[in] A pointer to the DriverProxy extension that the endpoints are registered to. This extension was created in a prior call to [**IoCreateDriverProxyExtension**](nf-wdm-iocreatedriverproxyextension.md).

### -param Endpoint

[in] A pointer to the endpoint function for which to find the wrapper. This must be a function pointer that was previously registered with [**IoRegisterDriverProxyEndpoints**](nf-wdm-ioregisterdriverproxyendpoints.md).

### -param Wrapper

[out] A pointer to a variable that receives a pointer to the wrapped endpoint function. If the endpoint is found, this will point to the wrapper function that should be called instead of the original endpoint.

## -returns

**IofGetDriverProxyWrapperFromEndpoint** returns one of the following NTSTATUS values:

| Return code | Description |
|-------------|-------------|
| **STATUS_SUCCESS** | The wrapper function was successfully found and returned. |
| **STATUS_NOT_FOUND** | The specified endpoint function was not found in the registered endpoints. |

## -remarks

This function is the standard method for retrieving endpoint wrappers in Driver Hot-Swap V2. The endpoint pointer passed to this function must exactly match a pointer that was identified during the automatic endpoint enumeration process.

To avoid compiler warnings when calling this function, you may need to cast the **Endpoint** and **Wrapper** parameters. For convenience, a macro **IoGetDriverProxyWrapperFromEndpoint** is provided that handles the type casting automatically. It is recommended to use the macro instead of calling this function directly.

The function can be called at any IRQL level and performs a fast lookup operation.

Once a wrapper is obtained, drivers should call the wrapper function instead of the original endpoint function to enable hot-swappable functionality.

## -see-also

- [**IoCreateDriverProxyExtension**](nf-wdm-iocreatedriverproxyextension.md)
- [**DRIVER_PROXY_ENDPOINT_FUNCTION**](nc-wdm-driver_proxy_endpoint_function.md)
