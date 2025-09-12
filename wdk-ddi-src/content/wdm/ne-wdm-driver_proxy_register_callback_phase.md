---
UID: NE:wdm._DRIVER_PROXY_REGISTER_CALLBACK_PHASE
tech.root: kernel
title: DRIVER_PROXY_REGISTER_CALLBACK_PHASE
ms.date: 09/11/2025
targetos: Windows
description: Defines the phases during which a DriverProxy register callback can be invoked.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: wdm.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: Universal
req.typenames: DRIVER_PROXY_REGISTER_CALLBACK_PHASE, *PDRIVER_PROXY_REGISTER_CALLBACK_PHASE
typedef_isUnnamed: false
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - wdm.h
api_name:
 - _DRIVER_PROXY_REGISTER_CALLBACK_PHASE
 - PDRIVER_PROXY_REGISTER_CALLBACK_PHASE
 - DRIVER_PROXY_REGISTER_CALLBACK_PHASE
f1_keywords:
 - _DRIVER_PROXY_REGISTER_CALLBACK_PHASE
 - wdm/_DRIVER_PROXY_REGISTER_CALLBACK_PHASE
 - PDRIVER_PROXY_REGISTER_CALLBACK_PHASE
 - wdm/PDRIVER_PROXY_REGISTER_CALLBACK_PHASE
 - DRIVER_PROXY_REGISTER_CALLBACK_PHASE
 - wdm/DRIVER_PROXY_REGISTER_CALLBACK_PHASE
dev_langs:
 - c++
helpviewer_keywords:
 - _DRIVER_PROXY_REGISTER_CALLBACK_PHASE
ai-usage: ai-generated
---

## -description

The **DRIVER_PROXY_REGISTER_CALLBACK_PHASE** enumeration defines the different phases during which a [**DRIVER_PROXY_REGISTER_CALLBACK**](nc-wdm-driver_proxy_register_callback.md) callback can be invoked during endpoint registration or hot-swap operations.

## -enum-fields

### -field DriverProxyRegisterCallbackPreProcess

Indicates the pre-processing phase. The callback is invoked before any endpoint function switching begins, allowing the driver to perform preparation operations such as acquiring locks, saving state, or notifying other components of the impending change.

### -field DriverProxyRegisterCallbackProxyStalled

Indicates the proxy stalled phase. The callback is invoked while all calls to registered endpoints are blocked (stalled). During this phase, the DriverProxy system has acquired the rundown lock and no new calls to endpoint functions will proceed. This is the safest time for the driver to perform operations that require exclusive access to resources that might be accessed by endpoint functions.

### -field DriverProxyRegisterCallbackPostProcess

Indicates the post-processing phase. The callback is invoked after endpoint function switching is complete and normal operation has resumed. This allows the driver to perform cleanup operations, release locks, update state, or notify other components that the hot-swap operation has completed.

### -field DriverProxyRegisterCallbackMax

Maximum value for the enumeration. This value is not used as a callback phase and is reserved for internal validation purposes.

## -remarks

This enumeration is used by [**IoRegisterDriverProxyEndpoints**](nf-wdm-ioregisterdriverproxyendpoints.md) to indicate which phase of the registration process is currently executing when the [**DRIVER_PROXY_REGISTER_CALLBACK**](nc-wdm-driver_proxy_register_callback.md) callback is invoked.

The callback phases occur in a specific sequence during endpoint registration or hot-swap operations:

1. **DriverProxyRegisterCallbackPreProcess**: Called before any function switching begins.
2. **DriverProxyRegisterCallbackProxyStalled**: Called while all endpoint calls are blocked.
3. **DriverProxyRegisterCallbackPostProcess**: Called after function switching is complete.

Each phase serves a different purpose in the hot-swap operation:

- The **PreProcess** phase allows drivers to prepare for the upcoming change.
- The **ProxyStalled** phase provides exclusive access when endpoint calls are blocked.
- The **PostProcess** phase allows drivers to clean up after the change is complete.

The callback must return **STATUS_SUCCESS** for the operation to continue. If any callback phase returns a failure status, the entire registration operation will fail and any partial changes will be rolled back.

## -see-also

[**DRIVER_PROXY_REGISTER_CALLBACK**](nc-wdm-driver_proxy_register_callback.md)

[**IoRegisterDriverProxyEndpoints**](nf-wdm-ioregisterdriverproxyendpoints.md)

[**DRIVER_PROXY_ENDPOINT_INFORMATION**](ns-wdm-driver_proxy_endpoint_information.md)
