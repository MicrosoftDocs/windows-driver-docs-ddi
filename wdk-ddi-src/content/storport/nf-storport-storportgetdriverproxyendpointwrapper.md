---
UID: NF:storport.StorPortGetDriverProxyEndpointWrapper
tech.root: storage
title: StorPortGetDriverProxyEndpointWrapper
ms.date: 07/26/2024
targetos: Windows
description: Learn more about the StorPortGetDriverProxyEndpointWrapper function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - StorPortGetDriverProxyEndpointWrapper
f1_keywords:
 - StorPortGetDriverProxyEndpointWrapper
 - storport/StorPortGetDriverProxyEndpointWrapper
dev_langs:
 - c++
helpviewer_keywords:
 - StorPortGetDriverProxyEndpointWrapper
---

## -description

**StorPortGetDriverProxyEndpointWrapper** retrieves the address of a wrapped function pointer for a driver's endpoint.

## -parameters

### -param HwDeviceExtension

[in] A pointer to the hardware device extension for the host bus adapter (HBA).

### -param ProxyExtension

[in] Pointer to an opaque structure that contains the driver proxy extension.

### -param Id

[in] The identifier of the driver's endpoint function.

### -param Wrapper

[out] Pointer to a location in which to receive the address of the wrapped function.

## -returns

**StorPortGetDriverProxyEndpointWrapper** returns **STOR_STATUS_SUCCESS** if the wrapper is sucessfully returned. Otherwise, it returns one of the following STOR_STATUS codes:

| Return code | Description |
| ----------- | ----------- |
| **STOR_STATUS_NOT_IMPLEMENTED** | This function is not implemented on the active operating system. |
| **STOR_STATUS_INVALID_PARAMETER** | The operation fails with this return value if one or more of the parameters are invalid. |

## -remarks

## -see-also

[**StorPortIsDriverHotSwapEnabled**](nf-storport-storportisdriverhotswapenabled.md)

[**StorPortRegisterDriverProxy**](nf-storport-storportregisterdriverproxy.md)

[**StorPortRegisterDriverProxyEndpoints**](nf-storport-storportregisterdriverproxyendpoints.md)
