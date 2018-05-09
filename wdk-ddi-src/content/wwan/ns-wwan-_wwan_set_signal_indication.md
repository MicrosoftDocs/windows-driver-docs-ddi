---
UID: NS:wwan._WWAN_SET_SIGNAL_INDICATION
title: "_WWAN_SET_SIGNAL_INDICATION"
author: windows-driver-content
description: The WWAN_SET_SIGNAL_INDICATION structure represents the frequency of RSSI interval and RSSI threshold notifications.
old-location: netvista\wwan_set_signal_indication.htm
old-project: netvista
ms.assetid: 266ec8f5-f6ec-47e5-b433-4f570f2d43d2
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PWWAN_SET_SIGNAL_INDICATION, PWWAN_SET_SIGNAL_INDICATION, PWWAN_SET_SIGNAL_INDICATION structure pointer [Network Drivers Starting with Windows Vista], WWAN_SET_SIGNAL_INDICATION, WWAN_SET_SIGNAL_INDICATION structure [Network Drivers Starting with Windows Vista], WwanRef_fa4b9dee-5b46-47f2-8674-d8fa78351d86.xml, _WWAN_SET_SIGNAL_INDICATION, netvista.wwan_set_signal_indication, wwan/PWWAN_SET_SIGNAL_INDICATION, wwan/WWAN_SET_SIGNAL_INDICATION"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	WWAN_SET_SIGNAL_INDICATION
product:
- Windows
targetos: Windows
req.typenames: WWAN_SET_SIGNAL_INDICATION, *PWWAN_SET_SIGNAL_INDICATION
---

# _WWAN_SET_SIGNAL_INDICATION structure


## -description


The WWAN_SET_SIGNAL_INDICATION structure represents the frequency of RSSI interval and RSSI threshold
  notifications.


## -struct-fields




### -field RssiInterval

The RSSI interval, in seconds.


### -field RssiThreshold

The RSSI threshold, in threshold units.


## -remarks



To minimize power consumption, the MB Service specifies a default interval and a default threshold for
    sending notifications that are based on an RSSI value that changes. In some situations, such as during
    long periods of user inactivity (in the case of the default interval), or in areas that have a strong
    signal (in the case of a default threshold), this value specifies when a longer interval or threshold (as
    appropriate) may be used to conserve additional power. However, miniport drivers are not required to
    adhere to an increased interval or threshold.

The WWAN_RSSI_DEFAULT value indicates that no suggested interval value is available, and that the
    miniport driver should use the default minimum interval or the default threshold (as appropriate). A
    value of WWAN_RSSI_DISABLE that the miniport driver will stop reporting the signal state based on the
    interval or threshold limit (as appropriate).

The miniport driver can always switch to its device-specific default reporting interval if the request
    in this member is outside of device limits.




## -see-also




<a href="https://msdn.microsoft.com/6ef6fdd4-7d52-436a-96ee-ed83fab33e7b">
   NDIS_WWAN_SET_SIGNAL_INDICATION</a>
 

 

