---
UID: NS:wwan._WWAN_DEVICE_SERVICE_SESSION
title: _WWAN_DEVICE_SERVICE_SESSION (wwan.h)
description: The WWAN_DEVICE_SERVICE_SESSION structure represents the state of a device service session, or the operation to be performed on a device service.
old-location: netvista\wwan_device_service_session.htm
tech.root: netvista
ms.assetid: 29EEB068-EFFB-42BF-8D92-D56D010DE46A
ms.date: 05/02/2018
keywords: ["_WWAN_DEVICE_SERVICE_SESSION structure"]
ms.keywords: "*PWWAN_DEVICE_SERVICE_SESSION, PWWAN_DEVICE_SERVICE_SESSION, PWWAN_DEVICE_SERVICE_SESSION structure pointer [Network Drivers Starting with Windows Vista], WWAN_DEVICE_SERVICE_SESSION, WWAN_DEVICE_SERVICE_SESSION structure [Network Drivers Starting with Windows Vista], _WWAN_DEVICE_SERVICE_SESSION, netvista.wwan_device_service_session, wwan/PWWAN_DEVICE_SERVICE_SESSION, wwan/WWAN_DEVICE_SERVICE_SESSION"
f1_keywords:
 - "wwan/WWAN_DEVICE_SERVICE_SESSION"
 - "WWAN_DEVICE_SERVICE_SESSION"
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
- WWAN_DEVICE_SERVICE_SESSION
product:
- Windows
targetos: Windows
req.typenames: WWAN_DEVICE_SERVICE_SESSION, *PWWAN_DEVICE_SERVICE_SESSION
---

# _WWAN_DEVICE_SERVICE_SESSION structure


## -description


The WWAN_DEVICE_SERVICE_SESSION structure represents the state of a device service session, or the operation to be performed on a device service.


## -struct-fields




### -field DeviceServiceGuid

The GUID of the device service on which to perform the operation.


### -field State

The state of, or action, for the device service session.


### -field uSessionID

The session ID for the device service session.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndiswwan/ns-ndiswwan-_ndis_wwan_device_service_session_info">NDIS_WWAN_DEVICE_SERVICE_SESSION_INFO</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndiswwan/ns-ndiswwan-_ndis_wwan_device_set_service_session">NDIS_WWAN_SET_DEVICE_SERVICE_SESSION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wwan/ne-wwan-_wwan_device_service_session_state">WWAN_DEVICE_SERVICE_SESSION_STATE</a>
 

 

