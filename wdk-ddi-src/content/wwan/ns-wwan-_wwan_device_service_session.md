---
UID: NS:wwan._WWAN_DEVICE_SERVICE_SESSION
title: "_WWAN_DEVICE_SERVICE_SESSION"
author: windows-driver-content
description: The WWAN_DEVICE_SERVICE_SESSION structure represents the state of a device service session, or the operation to be performed on a device service.
old-location: netvista\wwan_device_service_session.htm
old-project: netvista
ms.assetid: 29EEB068-EFFB-42BF-8D92-D56D010DE46A
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PWWAN_DEVICE_SERVICE_SESSION, wwan/PWWAN_DEVICE_SERVICE_SESSION, WWAN_DEVICE_SERVICE_SESSION structure [Network Drivers Starting with Windows Vista], _WWAN_DEVICE_SERVICE_SESSION, wwan/WWAN_DEVICE_SERVICE_SESSION, netvista.wwan_device_service_session, PWWAN_DEVICE_SERVICE_SESSION structure pointer [Network Drivers Starting with Windows Vista], WWAN_DEVICE_SERVICE_SESSION, *PWWAN_DEVICE_SERVICE_SESSION
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wwan.h
apiname:
-	WWAN_DEVICE_SERVICE_SESSION
product: Windows
targetos: Windows
req.typenames: "*PWWAN_DEVICE_SERVICE_SESSION, WWAN_DEVICE_SERVICE_SESSION"
req.product: Windows 10 or later.
---

# _WWAN_DEVICE_SERVICE_SESSION structure


## -description


The WWAN_DEVICE_SERVICE_SESSION structure represents the state of a device service session, or the operation to be performed on a device service.


## -syntax


````
typedef struct _WWAN_DEVICE_SERVICE_SESSION {
  GUID                              DeviceServiceGuid;
  WWAN_DEVICE_SERVICE_SESSION_STATE State;
  ULONG                             uSessionID;
} WWAN_DEVICE_SERVICE_SESSION, *PWWAN_DEVICE_SERVICE_SESSION;
````


## -struct-fields




#### - DeviceServiceGuid

The GUID of the device service on which to perform the operation.


#### - State

The state of, or action, for the device service session.


#### - uSessionID

The session ID for the device service session.


## -see-also

<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_device_set_service_session.md">NDIS_WWAN_SET_DEVICE_SERVICE_SESSION</a>

<a href="..\wwan\ne-wwan-_wwan_device_service_session_state.md">WWAN_DEVICE_SERVICE_SESSION_STATE</a>

<a href="..\ndiswwan\ns-ndiswwan-_ndis_wwan_device_service_session_info.md">NDIS_WWAN_DEVICE_SERVICE_SESSION_INFO</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_DEVICE_SERVICE_SESSION structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

