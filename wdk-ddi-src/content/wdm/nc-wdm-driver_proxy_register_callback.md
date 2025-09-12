---
UID: NC:wdm.DRIVER_PROXY_REGISTER_CALLBACK
tech.root: kernel
title: DRIVER_PROXY_REGISTER_CALLBACK
ms.date: 09/11/2025
targetos: Windows
description: Defines a callback routine that is invoked during different phases of DriverProxy endpoint registration.
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
 - DRIVER_PROXY_REGISTER_CALLBACK
f1_keywords:
 - DRIVER_PROXY_REGISTER_CALLBACK
 - wdm/DRIVER_PROXY_REGISTER_CALLBACK
dev_langs:
 - c++
helpviewer_keywords:
 - DRIVER_PROXY_REGISTER_CALLBACK
ai-usage: ai-generated
---

## -description

The **DRIVER_PROXY_REGISTER_CALLBACK** callback defines a routine that is invoked at different phases during DriverProxy endpoint registration and hot-swap operations.

## -parameters

### -param Phase

[in] A [**DRIVER_PROXY_REGISTER_CALLBACK_PHASE**](ne-wdm-driver_proxy_register_callback_phase.md) value that indicates which phase of the registration process is currently executing.

### -param Context

[in, optional] A pointer to driver-defined context information that was passed to [**IoRegisterDriverProxyEndpoints**](nf-wdm-ioregisterdriverproxyendpoints.md). This parameter can be NULL if no context was provided.

## -returns

**DRIVER_PROXY_REGISTER_CALLBACK** returns one of the following NTSTATUS values:

| Return code | Description |
|-------------|-------------|
| **STATUS_SUCCESS** | The callback completed successfully. The endpoint registration process will continue to the next phase. |
| **Other NTSTATUS values** | The callback encountered an error. The entire endpoint registration operation will fail and any partial changes will be rolled back. |

## -remarks

This callback allows drivers to perform custom operations at specific points during the endpoint registration process, enabling coordination with the hot-swap mechanism.

This callback is invoked by [**IoRegisterDriverProxyEndpoints**](nf-wdm-ioregisterdriverproxyendpoints.md) during endpoint registration and hot-swap operations. The callback runs at PASSIVE_LEVEL and provides drivers with the opportunity to coordinate with the DriverProxy system during critical phases of the hot-swap process.

The callback is invoked in a specific sequence during endpoint registration:

1. **Pre-processing phase**: Called before any endpoint function switching begins. Drivers can use this phase to prepare for the upcoming change, such as:
   - Acquiring driver-specific locks
   - Saving current state
   - Notifying other driver components
   - Preparing resources needed during the switch

2. **Proxy stalled phase**: Called while all calls to registered endpoints are blocked. During this phase, the DriverProxy system holds the rundown lock and no new calls to endpoint functions will proceed. This is the safest time to perform operations that require exclusive access to resources that might be accessed by endpoint functions, such as:
   - Updating shared data structures
   - Reconfiguring hardware
   - Modifying global driver state

3. **Post-processing phase**: Called after endpoint function switching is complete and normal operation has resumed. Drivers can use this phase for cleanup operations, such as:
   - Releasing driver-specific locks
   - Updating internal state
   - Notifying other components of completion
   - Logging or performance tracking

The callback must return **STATUS_SUCCESS** for the registration to continue. Any failure will cause the entire operation to fail and roll back.

During the **DriverProxyRegisterCallbackProxyStalled** phase, all endpoint calls are blocked, so the callback should perform operations quickly to minimize system disruption.

The callback should not perform operations that might call back into the same DriverProxy extension, as this could cause deadlocks.

The callback is optional and can be NULL if no driver-specific coordination is needed during endpoint registration.

## -see-also

[**IoRegisterDriverProxyEndpoints**](nf-wdm-ioregisterdriverproxyendpoints.md)

[**DRIVER_PROXY_REGISTER_CALLBACK_PHASE**](ne-wdm-driver_proxy_register_callback_phase.md)

[**DRIVER_PROXY_ENDPOINT_INFORMATION**](ns-wdm-driver_proxy_endpoint_information.md)

[**IoCreateDriverProxyExtension**](nf-wdm-iocreatedriverproxyextension.md)
