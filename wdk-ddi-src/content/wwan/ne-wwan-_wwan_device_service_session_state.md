---
UID: NE:wwan._WWAN_DEVICE_SERVICE_SESSION_STATE
title: "_WWAN_DEVICE_SERVICE_SESSION_STATE"
description: The WWAN_DEVICE_SERVICE_SESSION_STATE enumeration specifies the state of device service session. It can be used in a set operation to set the state of a session or can be used in an indication to report the state of a session.
old-location: netvista\wwan_device_service_session_state.htm
tech.root: netvista
ms.assetid: E2527150-2F62-4729-BC6A-FE6027BCCA35
ms.date: 05/02/2018
ms.keywords: "*PWWAN_DEVICE_SERVICE_SESSION_STATE, WWAN_DEVICE_SERVICE_SESSION_STATE, WWAN_DEVICE_SERVICE_SESSION_STATE enumeration [Network Drivers Starting with Windows Vista], WwanDeviceServiceSessionClosed, WwanDeviceServiceSessionOpen, _WWAN_DEVICE_SERVICE_SESSION_STATE, netvista.wwan_device_service_session_state, wwan/WWAN_DEVICE_SERVICE_SESSION_STATE, wwan/WwanDeviceServiceSessionClosed, wwan/WwanDeviceServiceSessionOpen"
ms.topic: enum
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wwan.h
api_name:
-	WWAN_DEVICE_SERVICE_SESSION_STATE
product:
- Windows
targetos: Windows
req.typenames: WWAN_DEVICE_SERVICE_SESSION_STATE, *PWWAN_DEVICE_SERVICE_SESSION_STATE
---

# _WWAN_DEVICE_SERVICE_SESSION_STATE enumeration


## -description


The WWAN_DEVICE_SERVICE_SESSION_STATE enumeration specifies the state of device service session. It can be used in a set operation to set the state of a session or can be used in an indication to report the state of a session.


## -enum-fields




### -field WwanDeviceServiceSessionOpen

The device service session is closed or should be closed.


### -field WwanDeviceServiceSessionClosed

The device service session is open or should be opened.


## -remarks



The WWAN_DEVICE_SERVICE_SESSION structure uses the WWAN_DEVICE_SERVICE_SESSION_STATE enumeration to set or report the state of a session.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh831873">WWAN_DEVICE_SERVICE_SESSION</a>
 

 

