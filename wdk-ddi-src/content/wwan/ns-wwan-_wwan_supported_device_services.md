---
UID: NS:wwan._WWAN_SUPPORTED_DEVICE_SERVICES
title: _WWAN_SUPPORTED_DEVICE_SERVICES (wwan.h)
description: The WWAN_SUPPORTED_DEVICE_SERVICES structure describes information about device services supported by the miniport driver.
old-location: netvista\wwan_supported_device_services.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WWAN_SUPPORTED_DEVICE_SERVICES structure"]
ms.keywords: "*PWWAN_SUPPORTED_DEVICE_SERVICES, PWWAN_SUPPORTED_DEVICE_SERVICES, PWWAN_SUPPORTED_DEVICE_SERVICES structure pointer [Network Drivers Starting with Windows Vista], WWAN_SUPPORTED_DEVICE_SERVICES, WWAN_SUPPORTED_DEVICE_SERVICES structure [Network Drivers Starting with Windows Vista], _WWAN_SUPPORTED_DEVICE_SERVICES, netvista.wwan_supported_device_services, wwan/PWWAN_SUPPORTED_DEVICE_SERVICES, wwan/WWAN_SUPPORTED_DEVICE_SERVICES"
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
req.typenames: WWAN_SUPPORTED_DEVICE_SERVICES, *PWWAN_SUPPORTED_DEVICE_SERVICES
f1_keywords:
 - _WWAN_SUPPORTED_DEVICE_SERVICES
 - wwan/_WWAN_SUPPORTED_DEVICE_SERVICES
 - PWWAN_SUPPORTED_DEVICE_SERVICES
 - wwan/PWWAN_SUPPORTED_DEVICE_SERVICES
 - WWAN_SUPPORTED_DEVICE_SERVICES
 - wwan/WWAN_SUPPORTED_DEVICE_SERVICES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - _WWAN_SUPPORTED_DEVICE_SERVICES
 - PWWAN_SUPPORTED_DEVICE_SERVICES
 - WWAN_SUPPORTED_DEVICE_SERVICES
---

# _WWAN_SUPPORTED_DEVICE_SERVICES structure


## -description

The WWAN_SUPPORTED_DEVICE_SERVICES structure describes information about device services supported by the miniport driver.

## -struct-fields

### -field uMaxCommandDataSize

The maximum size, in bytes, of data that can be associated with a device service command.

### -field uMaxSessionDataSize

The maximum size, in bytes, of data that can be associated with a device service session.

### -field uMaxSessionCount

The maximum number of device service sessions supported by the miniport driver.

### -field ListHeader

A formatted WWAN_LIST_HEADER object that represents a list of supported device services and the number of services  in the list.

This member points to the list of the <a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_device_service_entry">WWAN_DEVICE_SERVICE_ENTRY</a> by using the WWAN_LIST_HEADER structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndiswwan/ns-ndiswwan-_ndis_wwan_supported_device_services">NDIS_WWAN_SUPPORTED_DEVICE_SERVICES</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_device_service_entry">WWAN_DEVICE_SERVICE_ENTRY</a>



<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_list_header">WWAN_LIST_HEADER</a>

