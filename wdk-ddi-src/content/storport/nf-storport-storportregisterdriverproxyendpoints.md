---
UID: NF:storport.StorPortRegisterDriverProxyEndpoints
tech.root: display
title: StorPortRegisterDriverProxyEndpoints
ms.date: 07/26/2024
targetos: Windows
description: Learn more about the StorPortRegisterDriverProxyEndpoints function.
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
 - StorPortRegisterDriverProxyEndpoints
f1_keywords:
 - StorPortRegisterDriverProxyEndpoints
 - storport/StorPortRegisterDriverProxyEndpoints
dev_langs:
 - c++
helpviewer_keywords:
 - StorPortRegisterDriverProxyEndpoints
---

## -description

**StorPortRegisterDriverProxyEndpoints** registers driver proxy endpoints with the kernel.

## -parameters

### -param HwDeviceExtension

[in] A pointer to the hardware device extension for the host bus adapter (HBA).

### -param ProxyExtension

[in] Pointer to opaque data that contains the driver proxy extension. Storport returns this information when the miniport driver calls [**StorPortRegisterDriverProxy**](nf-storport-storportregisterdriverproxy.md).

### -param EndpointInfo

[in/out] Pointer to an array of [**STOR_DRIVER_PROXY_ENDPOINT_INFORMATION**](ns-storport-stor_driver_proxy_endpoint_information.md) structures that contain the driver proxy endpoint information.

### -param Count

[in] The number of elements in the array that **EndpointInfo** points to.

## -returns

**StorPortRegisterDriverProxyEndpoints** returns one of the following STOR_STATUS codes:

| Return code | Description |
| ----------- | ----------- |
| **STOR_STATUS_NOT_IMPLEMENTED** | This function is not implemented on the active operating system. |
| **STOR_STATUS_SUCCESS** | The operation was successful. |
| **STOR_STATUS_INVALID_PARAMETER** | The operation fails with this return value if one or more of the parameters are invalid. |

## -remarks

## -see-also

[**STOR_DRIVER_PROXY_ENDPOINT_INFORMATION**](ns-storport-stor_driver_proxy_endpoint_information.md)

[**StorPortGetDriverProxyEndpointWrapper**](nf-storport-storportgetdriverproxyendpointwrapper.md)

[**StorPortRegisterDriverProxy**](nf-storport-storportregisterdriverproxy.md)
