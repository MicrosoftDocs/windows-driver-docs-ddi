---
UID: NF:wdm.IoGetDriverProxyWrapperFromEndpoint
tech.root: kernel
title: IoGetDriverProxyWrapperFromEndpoint
ms.date: 09/09/2025
targetos: Windows
description: Gets the wrapper for an endpoint function using the endpoint function pointer (macro).
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
req.lib: 
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
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - IoGetDriverProxyWrapperFromEndpoint
f1_keywords:
 - IoGetDriverProxyWrapperFromEndpoint
 - wdm/IoGetDriverProxyWrapperFromEndpoint
dev_langs:
 - c++
helpviewer_keywords:
 - IoGetDriverProxyWrapperFromEndpoint
ai-usage: ai-assisted
---

## -description

The **IoGetDriverProxyWrapperFromEndpoint** macro gets the pointer to the wrapper for an endpoint function using the endpoint function pointer. This macro provides a convenient wrapper around [**IofGetDriverProxyWrapperFromEndpoint**](nf-wdm-iofgetdriverproxywrapperfromendpoint.md) with automatic type casting.

This macro is the standard method for retrieving endpoint wrappers in Driver Hot-Swap V2. It handles the type casting automatically and provides a cleaner interface compared to calling the underlying function directly.

## -parameters

### -param DriverProxyExtension

[in] A pointer to the DriverProxy extension that the endpoints are registered to. This extension was created in a prior call to [**IoCreateDriverProxyExtension**](nf-wdm-iocreatedriverproxyextension.md).

### -param Endpoint

[in] A pointer to a [**DRIVER_PROXY_ENDPOINT_FUNCTION**](nc-wdm-driver_proxy_endpoint_function.md) endpoint function for which to find the wrapper. This must be a function pointer that was identified during the automatic endpoint enumeration process in Driver Hot-Swap V2.

### -param Wrapper

[out] A pointer to a variable that receives a pointer to a [**DRIVER_PROXY_ENDPOINT_FUNCTION**](nc-wdm-driver_proxy_endpoint_function.md) wrapper function. If the endpoint is found, **Wrapper** will be set to point to the wrapper function that should be called instead of the original endpoint. If the endpoint isn't found, **Wrapper** is set to NULL.

## -remarks

This macro is designed for Driver Hot-Swap V2, which uses automatic compiler-based endpoint enumeration rather than manual endpoint registration. The endpoint pointer passed to this macro must exactly match a pointer that was identified during the automatic endpoint enumeration process.

The macro handles type casting automatically, making it more convenient to use than the underlying [**IofGetDriverProxyWrapperFromEndpoint**](nf-wdm-iofgetdriverproxywrapperfromendpoint.md) function. This eliminates potential compiler warnings related to pointer type conversions.

The macro can be used at any IRQL level and performs a fast lookup operation.

Once a wrapper is obtained, drivers should call the wrapper function instead of the original endpoint function to enable hot-swappable functionality. This allows the function implementation to be replaced at runtime without unloading the driver.

In Driver Hot-Swap V2, endpoints are automatically discovered and registered during the build process through compiler and linker analysis of the `.shsept` section, eliminating the need for manual endpoint registration.

## -see-also

[**IofGetDriverProxyWrapperFromEndpoint**](nf-wdm-iofgetdriverproxywrapperfromendpoint.md)

[**IoCreateDriverProxyExtension**](nf-wdm-iocreatedriverproxyextension.md)

[**DRIVER_PROXY_ENDPOINT_FUNCTION**](nc-wdm-driver_proxy_endpoint_function.md)
