---
UID: NE:wwan._WWAN_EMERGENCY_MODE
title: "_WWAN_EMERGENCY_MODE"
author: windows-driver-content
description: The WWAN_EMERGENCY_MODE enumeration lists the different types of emergency modes that are supported by the MB device.
old-location: netvista\wwan_emergency_mode.htm
old-project: netvista
ms.assetid: d901e763-5e1c-443d-ba9c-9d1e4413bd47
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PWWAN_EMERGENCY_MODE, PWWAN_EMERGENCY_MODE, PWWAN_EMERGENCY_MODE enumeration pointer [Network Drivers Starting with Windows Vista], WWAN_EMERGENCY_MODE, WWAN_EMERGENCY_MODE enumeration [Network Drivers Starting with Windows Vista], WwanEmergencyModeMax, WwanEmergencyModeOff, WwanEmergencyModeOn, WwanRef_8b2029ff-7d10-4f36-a4c0-6b41f464b726.xml, _WWAN_EMERGENCY_MODE, netvista.wwan_emergency_mode, wwan/PWWAN_EMERGENCY_MODE, wwan/WWAN_EMERGENCY_MODE, wwan/WwanEmergencyModeMax, wwan/WwanEmergencyModeOff, wwan/WwanEmergencyModeOn"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of Windows.
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
-	WWAN_EMERGENCY_MODE
product: Windows
targetos: Windows
req.typenames: WWAN_EMERGENCY_MODE, *PWWAN_EMERGENCY_MODE
req.product: Windows 10 or later.
---

# _WWAN_EMERGENCY_MODE enumeration


## -description


The WWAN_EMERGENCY_MODE enumeration lists the different types of emergency modes that are supported
  by the MB device.


## -syntax


````
typedef enum _WWAN_EMERGENCY_MODE { 
  WwanEmergencyModeOff  = 0,
  WwanEmergencyModeOn,
  WwanEmergencyModeMax
} WWAN_EMERGENCY_MODE, *PWWAN_EMERGENCY_MODE;
````


## -enum-fields




### -field WwanEmergencyModeOff

The device is in normal mode.


### -field WwanEmergencyModeOn

The device is in emergency mode. An example of an emergency mode function is a call to 911.


### -field WwanEmergencyModeMax

The total number of supported emergency modes.


## -see-also

<a href="..\wwan\ns-wwan-_wwan_ready_info.md">WWAN_READY_INFO</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_EMERGENCY_MODE enumeration%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

