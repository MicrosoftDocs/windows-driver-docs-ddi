---
UID: NC:wdm.DRIVER_PROXY_ENDPOINT_FUNCTION
tech.root: kernel
title: DRIVER_PROXY_ENDPOINT_FUNCTION
ms.date: 09/09/2025
targetos: Windows
description: Defines the function signature for a hot-swappable endpoint function in the DriverProxy system.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: wdm.h
req.idl: 
req.include-header: 
req.irql: Variable
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
 - UserDefined
api_location:
 - wdm.h
api_name:
 - DRIVER_PROXY_ENDPOINT_FUNCTION
f1_keywords:
 - DRIVER_PROXY_ENDPOINT_FUNCTION
 - wdm/DRIVER_PROXY_ENDPOINT_FUNCTION
dev_langs:
 - c++
helpviewer_keywords:
 - DRIVER_PROXY_ENDPOINT_FUNCTION
ai-usage: ai-assisted
---

## -description

The **DRIVER_PROXY_ENDPOINT_FUNCTION** callback defines the function signature for a hot-swappable endpoint function in the DriverProxy system. This is a generic function pointer type that represents any driver function that can be made hot-swappable through the Driver Hot-Swap framework.

## -remarks

Endpoint functions are driver-implemented functions that can be replaced at runtime without unloading the driver. The DriverProxy system creates wrapper functions that redirect calls to the current implementation of each endpoint function, enabling hot-swap functionality.

This callback type serves as a generic function pointer for the DriverProxy system. In practice, endpoint functions will have different signatures depending on their specific purpose, but they are all treated as **DRIVER_PROXY_ENDPOINT_FUNCTION** pointers within the DriverProxy infrastructure.

In Driver Hot-Swap V2, endpoint functions are automatically discovered during the build process through compiler and linker analysis. The compiler identifies functions that should be hot-swappable and places information about them in the `.shsept` section of the binary.

Key characteristics of endpoint functions:

- They can be replaced at runtime through the DriverProxy system
- They are accessed through wrapper functions returned by [**IoGetDriverProxyWrapperFromEndpoint**](nf-wdm-iogetdriverproxywrapperfromendpoint.md)
- They must be associated with a DriverProxy extension created by [**IoCreateDriverProxyExtension**](nf-wdm-iocreatedriverproxyextension.md)
- Their replacement is coordinated through the DriverProxy infrastructure to ensure thread safety

The actual IRQL requirements for endpoint functions depend on the specific function being implemented. Drivers should design their endpoint functions according to the IRQL constraints of their intended usage.

## -see-also

[**IoGetDriverProxyWrapperFromEndpoint**](nf-wdm-iogetdriverproxywrapperfromendpoint.md)

[**IofGetDriverProxyWrapperFromEndpoint**](nf-wdm-iofgetdriverproxywrapperfromendpoint.md)

[**IoCreateDriverProxyExtension**](nf-wdm-iocreatedriverproxyextension.md)

[**DRIVER_PROXY_ENDPOINT_INFORMATION**](ns-wdm-driver_proxy_endpoint_information.md)
