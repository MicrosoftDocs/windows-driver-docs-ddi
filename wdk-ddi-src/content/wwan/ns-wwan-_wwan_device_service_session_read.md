---
UID: NS:wwan._WWAN_DEVICE_SERVICE_SESSION_READ
title: _WWAN_DEVICE_SERVICE_SESSION_READ (wwan.h)
description: The WWAN_DEVICE_SERVICE_SESSION_READ structure represents data associated with a device service session read notification.
old-location: netvista\wwan_device_service_session_read.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WWAN_DEVICE_SERVICE_SESSION_READ structure"]
ms.keywords: "*PWWAN_DEVICE_SERVICE_SESSION_READ, PWWAN_DEVICE_SERVICE_SESSION_READ, PWWAN_DEVICE_SERVICE_SESSION_READ structure pointer [Network Drivers Starting with Windows Vista], WWAN_DEVICE_SERVICE_SESSION_READ, WWAN_DEVICE_SERVICE_SESSION_READ structure [Network Drivers Starting with Windows Vista], _WWAN_DEVICE_SERVICE_SESSION_READ, netvista.wwan_device_service_session_read, wwan/PWWAN_DEVICE_SERVICE_SESSION_READ, wwan/WWAN_DEVICE_SERVICE_SESSION_READ"
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
targetos: Windows
req.typenames: WWAN_DEVICE_SERVICE_SESSION_READ, *PWWAN_DEVICE_SERVICE_SESSION_READ
f1_keywords:
 - _WWAN_DEVICE_SERVICE_SESSION_READ
 - wwan/_WWAN_DEVICE_SERVICE_SESSION_READ
 - PWWAN_DEVICE_SERVICE_SESSION_READ
 - wwan/PWWAN_DEVICE_SERVICE_SESSION_READ
 - WWAN_DEVICE_SERVICE_SESSION_READ
 - wwan/WWAN_DEVICE_SERVICE_SESSION_READ
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - WWAN_DEVICE_SERVICE_SESSION_READ
---

# _WWAN_DEVICE_SERVICE_SESSION_READ structure


## -description

The WWAN_DEVICE_SERVICE_SESSION_READ structure represents data associated with a device service session read notification.

## -struct-fields

### -field uSessionID

The session ID of the device service.

### -field uDataSize

The size, in bytes, of the device service data that follows the structure instance in memory. This value should not exceed the value of the <b>uMaxSessionDataSize</b> member of the <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_supported_device_services">WWAN_SUPPORTED_DEVICE_SERVICES</a> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndiswwan/ns-ndiswwan-_ndis_wwan_device_service_session_read">NDIS_WWAN_DEVICE_SERVICE_SESSION_READ</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_supported_device_services">WWAN_SUPPORTED_DEVICE_SERVICES</a>
