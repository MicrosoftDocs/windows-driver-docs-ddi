---
UID: NF:storport.StorPortRegisterDriverProxy
tech.root: storage
title: StorPortRegisterDriverProxy
ms.date: 07/25/2024
targetos: Windows
description: Learn more about the StorPortRegisterDriverProxy function.
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
 - StorPortRegisterDriverProxy
f1_keywords:
 - StorPortRegisterDriverProxy
 - storport/StorPortRegisterDriverProxy
dev_langs:
 - c++
helpviewer_keywords:
 - StorPortRegisterDriverProxy
---

## -description

**StorPortRegisterDriverProxy** creates a driver proxy endpoint for the specified driver object.

## -parameters

### -param HwDeviceExtension

[in] A pointer to the hardware device extension for the host bus adapter (HBA).

### -param DriverObject

[in] A pointer to the driver object.

### -param ProxyExtension

[out] Pointer to StorPort's opaque data that contains the allocated driver proxy extension.

## -returns

**StorPortRegisterDriverProxy** returns one of the following status codes:

| Return code | Description |
| ----------- | ----------- |
| **STOR_STATUS_NOT_IMPLEMENTED** | This function is not implemented on the active operating system. |
| **STOR_STATUS_SUCCESS** | The operation was successful. |
| **STOR_STATUS_INVALID_PARAMETER** | The operation fails with this return value if one or more of the parameters are invalid. |

## -remarks

## -see-also

[**StorPortGetDriverProxyEndpointWrapper**](nf-storport-storportgetdriverproxyendpointwrapper.md)

[**StorPortRegisterDriverProxyEndpoints**](nf-storport-storportregisterdriverproxyendpoints.md)
