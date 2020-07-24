---
UID: NS:wwan._WWAN_DEVICE_SERVICE_RESPONSE
title: _WWAN_DEVICE_SERVICE_RESPONSE (wwan.h)
description: The WWAN_DEVICE_SERVICE_RESPONSE structure represents a response from a device service.
old-location: netvista\wwan_device_service_response.htm
tech.root: netvista
ms.assetid: FCDAEE07-B10E-491B-9BDB-49D77444281D
ms.date: 05/02/2018
keywords: ["_WWAN_DEVICE_SERVICE_RESPONSE structure"]
ms.keywords: "*PWWAN_DEVICE_SERVICE_RESPONSE, PWWAN_DEVICE_SERVICE_RESPONSE, PWWAN_DEVICE_SERVICE_RESPONSE structure pointer [Network Drivers Starting with Windows Vista], WWAN_DEVICE_SERVICE_RESPONSE, WWAN_DEVICE_SERVICE_RESPONSE structure [Network Drivers Starting with Windows Vista], _WWAN_DEVICE_SERVICE_RESPONSE, netvista.wwan_device_service_response, wwan/PWWAN_DEVICE_SERVICE_RESPONSE, wwan/WWAN_DEVICE_SERVICE_RESPONSE"
f1_keywords:
 - "wwan/WWAN_DEVICE_SERVICE_RESPONSE"
 - "WWAN_DEVICE_SERVICE_RESPONSE"
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- wwan.h
api_name:
- WWAN_DEVICE_SERVICE_RESPONSE
targetos: Windows
req.typenames: WWAN_DEVICE_SERVICE_RESPONSE, *PWWAN_DEVICE_SERVICE_RESPONSE
---

# _WWAN_DEVICE_SERVICE_RESPONSE structure


## -description


The WWAN_DEVICE_SERVICE_RESPONSE structure represents a response from a device service.


## -struct-fields




### -field DeviceServiceGuid

The GUID of the device service that the response originated from.


### -field ResponseID

The ID of the response.


### -field uDataSize

The size, in bytes, of the device service response data that follows the structure instance in memory. This value should not exceed the value of the <b>uMaxCommandDataSize</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_supported_device_services">WWAN_SUPPORTED_DEVICE_SERVICES</a> structure.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_supported_device_services">WWAN_SUPPORTED_DEVICE_SERVICES</a>
 

 

