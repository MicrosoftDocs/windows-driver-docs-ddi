---
UID: NS:storport._STOR_DRIVER_PROXY_ENDPOINT_INFORMATION
tech.root: storage
title: STOR_DRIVER_PROXY_ENDPOINT_INFORMATION
ms.date: 07/25/2024
targetos: Windows
description: Learn more about the STOR_DRIVER_PROXY_ENDPOINT_INFORMATION structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2
req.target-min-winversvr: 
req.target-type: 
req.typenames: STOR_DRIVER_PROXY_ENDPOINT_INFORMATION, *PSTOR_DRIVER_PROXY_ENDPOINT_INFORMATION
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - _STOR_DRIVER_PROXY_ENDPOINT_INFORMATION
 - PSTOR_DRIVER_PROXY_ENDPOINT_INFORMATION
 - STOR_DRIVER_PROXY_ENDPOINT_INFORMATION
f1_keywords:
 - _STOR_DRIVER_PROXY_ENDPOINT_INFORMATION
 - storport/_STOR_DRIVER_PROXY_ENDPOINT_INFORMATION
 - PSTOR_DRIVER_PROXY_ENDPOINT_INFORMATION
 - storport/PSTOR_DRIVER_PROXY_ENDPOINT_INFORMATION
 - STOR_DRIVER_PROXY_ENDPOINT_INFORMATION
 - storport/STOR_DRIVER_PROXY_ENDPOINT_INFORMATION
dev_langs:
 - c++
helpviewer_keywords:
 - _STOR_DRIVER_PROXY_ENDPOINT_INFORMATION
---

## -description

The **STOR_DRIVER_PROXY_ENDPOINT_INFORMATION** structure contains information about a driver proxy endpoint.

## -struct-fields

### -field Id

Unique identifier for the endpoint function that **EndpointFunction** points to.

### -field EndpointFunction

Pointer to the driver's endpoint function. **EndpointFunction** must point to a function that has **ParameterCount** parameters.

### -field ParameterCount

Number of parameters that the endpoint function takes.

## -remarks

## -see-also

[**StorPortRegisterDriverProxyEndpoints**](nf-storport-storportregisterdriverproxyendpoints.md)
