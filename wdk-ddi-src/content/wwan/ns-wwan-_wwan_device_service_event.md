---
UID: NS:wwan._WWAN_DEVICE_SERVICE_EVENT
title: _WWAN_DEVICE_SERVICE_EVENT (wwan.h)
description: The WWAN_DEVICE_SERVICE_EVENT structure represents an unsolicited device service event.
old-location: netvista\wwan_device_service_event.htm
tech.root: netvista
ms.assetid: 7E02DDE0-7D55-4FBD-879E-EFBA6A517D86
ms.date: 05/02/2018
ms.keywords: "*PWWAN_DEVICE_SERVICE_EVENT, PWWAN_DEVICE_SERVICE_EVENT, PWWAN_DEVICE_SERVICE_EVENT structure pointer [Network Drivers Starting with Windows Vista], WWAN_DEVICE_SERVICE_EVENT, WWAN_DEVICE_SERVICE_EVENT structure [Network Drivers Starting with Windows Vista], _WWAN_DEVICE_SERVICE_EVENT, netvista.wwan_device_service_event, wwan/PWWAN_DEVICE_SERVICE_EVENT, wwan/WWAN_DEVICE_SERVICE_EVENT"
ms.topic: struct
f1_keywords:
 - "wwan/WWAN_DEVICE_SERVICE_EVENT"
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
- WWAN_DEVICE_SERVICE_EVENT
product:
- Windows
targetos: Windows
req.typenames: WWAN_DEVICE_SERVICE_EVENT, *PWWAN_DEVICE_SERVICE_EVENT
---

# _WWAN_DEVICE_SERVICE_EVENT structure


## -description


The WWAN_DEVICE_SERVICE_EVENT structure represents an unsolicited device service event.


## -struct-fields




### -field DeviceServiceGuid

The GUID of the device service that the event originated from.


### -field EventID

The ID for the event.


### -field uDataSize

The size, in bytes, of the device service event data that follows the structure instance in memory. This value should not exceed the value of the <b>uMaxCommandDataSize</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_supported_device_services">WWAN_SUPPORTED_DEVICE_SERVICES</a> structure.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_supported_device_services">WWAN_SUPPORTED_DEVICE_SERVICES</a>
 

 

