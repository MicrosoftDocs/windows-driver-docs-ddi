---
UID: NS:wwan._WWAN_DEVICE_SERVICE_ENTRY
title: _WWAN_DEVICE_SERVICE_ENTRY (wwan.h)
description: The WWAN_DEVICE_SERVICE_ENTRY structure describes information about a device service.
old-location: netvista\wwan_device_service_entry.htm
tech.root: netvista
ms.assetid: 26B26715-0C1E-4FF1-B3FA-B6952BF70572
ms.date: 05/02/2018
ms.keywords: "*PWWAN_DEVICE_SERVICE_ENTRY, PWWAN_DEVICE_SERVICE_ENTRY, PWWAN_DEVICE_SERVICE_ENTRY structure pointer [Network Drivers Starting with Windows Vista], WWAN_DEVICE_SERVICE_ENTRY, WWAN_DEVICE_SERVICE_ENTRY structure [Network Drivers Starting with Windows Vista], _WWAN_DEVICE_SERVICE_ENTRY, netvista.wwan_device_service_entry, wwan/PWWAN_DEVICE_SERVICE_ENTRY, wwan/WWAN_DEVICE_SERVICE_ENTRY"
ms.topic: struct
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
- WWAN_DEVICE_SERVICE_ENTRY
product:
- Windows
targetos: Windows
req.typenames: WWAN_DEVICE_SERVICE_ENTRY, *PWWAN_DEVICE_SERVICE_ENTRY
---

# _WWAN_DEVICE_SERVICE_ENTRY structure


## -description


The WWAN_DEVICE_SERVICE_ENTRY structure describes information about a device service.


## -struct-fields




### -field DeviceServiceGuid

The GUID of the device service. This GUID is used to identify the device service in any of the other device OIDs/indications.


### -field SessionCapability

Flags indicating the capabilities of a device service session.


### -field uMaxSessionInstances

The maximum number of sessions supported by the device service.


## -remarks



Device service OIDs and NDIS Status Notifications use the device service's GUID to identify the device service.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh831874">WWAN_DEVICE_SERVICE_SESSION_CAPABILITY</a>
 

 

