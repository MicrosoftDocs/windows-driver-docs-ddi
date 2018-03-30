---
UID: NE:wwan._WWAN_DEVICE_SERVICE_SESSION_STATE
title: "_WWAN_DEVICE_SERVICE_SESSION_STATE"
author: windows-driver-content
description: The WWAN_DEVICE_SERVICE_SESSION_STATE enumeration specifies the state of device service session. It can be used in a set operation to set the state of a session or can be used in an indication to report the state of a session.
old-location: netvista\wwan_device_service_session_state.htm
old-project: netvista
ms.assetid: E2527150-2F62-4729-BC6A-FE6027BCCA35
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PWWAN_DEVICE_SERVICE_SESSION_STATE, WWAN_DEVICE_SERVICE_SESSION_STATE, WWAN_DEVICE_SERVICE_SESSION_STATE enumeration [Network Drivers Starting with Windows Vista], WwanDeviceServiceSessionClosed, WwanDeviceServiceSessionOpen, _WWAN_DEVICE_SERVICE_SESSION_STATE, netvista.wwan_device_service_session_state, wwan/WWAN_DEVICE_SERVICE_SESSION_STATE, wwan/WwanDeviceServiceSessionClosed, wwan/WwanDeviceServiceSessionOpen"
ms.prod: windows-hardware
ms.technology: windows-devices
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
product: Windows
targetos: Windows
req.typenames: WWAN_DEVICE_SERVICE_SESSION_STATE, *PWWAN_DEVICE_SERVICE_SESSION_STATE
req.product: Windows 10 or later.
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
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_DEVICE_SERVICE_SESSION_STATE enumeration%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
