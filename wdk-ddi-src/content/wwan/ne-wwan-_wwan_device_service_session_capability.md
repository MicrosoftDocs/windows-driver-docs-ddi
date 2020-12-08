---
UID: NE:wwan._WWAN_DEVICE_SERVICE_SESSION_CAPABILITY
title: _WWAN_DEVICE_SERVICE_SESSION_CAPABILITY (wwan.h)
description: The WWAN_DEVICE_SERVICE_SESSION_CAPABILITY enumeration lists the different device service session operations that are supported by the device service.
old-location: netvista\wwan_device_service_session_capability.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["WWAN_DEVICE_SERVICE_SESSION_CAPABILITY enumeration"]
ms.keywords: "*PWWAN_DEVICE_SERVICE_SESSION_CAPABILITY, WWAN_DEVICE_SERVICE_SESSION_CAPABILITY, WWAN_DEVICE_SERVICE_SESSION_CAPABILITY enumeration [Network Drivers Starting with Windows Vista], WwanDeviceServiceSessionNotSupported, WwanDeviceServiceSessionReadSupported, WwanDeviceServiceSessionWriteSupported, _WWAN_DEVICE_SERVICE_SESSION_CAPABILITY, netvista.wwan_device_service_session_capability, wwan/WWAN_DEVICE_SERVICE_SESSION_CAPABILITY, wwan/WwanDeviceServiceSessionNotSupported, wwan/WwanDeviceServiceSessionReadSupported, wwan/WwanDeviceServiceSessionWriteSupported"
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 8.
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
req.typenames: WWAN_DEVICE_SERVICE_SESSION_CAPABILITY, *PWWAN_DEVICE_SERVICE_SESSION_CAPABILITY
f1_keywords:
 - _WWAN_DEVICE_SERVICE_SESSION_CAPABILITY
 - wwan/_WWAN_DEVICE_SERVICE_SESSION_CAPABILITY
 - PWWAN_DEVICE_SERVICE_SESSION_CAPABILITY
 - wwan/PWWAN_DEVICE_SERVICE_SESSION_CAPABILITY
 - WWAN_DEVICE_SERVICE_SESSION_CAPABILITY
 - wwan/WWAN_DEVICE_SERVICE_SESSION_CAPABILITY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wwan.h
api_name:
 - WWAN_DEVICE_SERVICE_SESSION_CAPABILITY
---

# _WWAN_DEVICE_SERVICE_SESSION_CAPABILITY enumeration


## -description

The WWAN_DEVICE_SERVICE_SESSION_CAPABILITY enumeration lists the different device service session operations that are supported by the device service.

## -enum-fields

### -field WwanDeviceServiceSessionNotSupported

The device service does not support device service sessions.

### -field WwanDeviceServiceSessionWriteSupported

The device service supports write operations from Windows to the miniport driver.

### -field WwanDeviceServiceSessionReadSupported

The device service supports read indication  notifications on a session for data read from the device.

## -see-also

<a href="/windows-hardware/drivers/ddi/wwan/ns-wwan-_wwan_device_service_entry">WWAN_DEVICE_SERVICE_ENTRY</a>
