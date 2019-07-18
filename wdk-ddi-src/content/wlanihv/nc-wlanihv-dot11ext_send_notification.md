---
UID: NC:wlanihv.DOT11EXT_SEND_NOTIFICATION
title: DOT11EXT_SEND_NOTIFICATION (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extsendnotification.htm
tech.root: netvista
ms.assetid: 8191b375-537e-44df-920e-077c77ed2354
ms.date: 02/16/2018
ms.keywords: DOT11EXT_SEND_NOTIFICATION, Dot11ExtSendNotification, Dot11ExtSendNotification callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_163e65f4-108a-4d10-bcf7-b487bd3cc0c9.xml, netvista.dot11extsendnotification, wlanihv/Dot11ExtSendNotification
ms.topic: callback
f1_keywords:
 - "wlanihv/Dot11ExtSendNotification"
req.header: wlanihv.h
req.include-header: Wlanihv.h, L2cmn.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
- UserDefined
api_location:
- wlanihv.h
api_name:
- Dot11ExtSendNotification
product:
- Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXT_SEND_NOTIFICATION callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div>

The IHV Extensions DLL calls the
  <b>Dot11ExtSendNotification</b> function to send notifications to any service or
  application that has registered for the notification.


## -prototype


```cpp
DWORD WINAPI * Dot11ExtSendNotification(
  _In_opt_ HANDLE                hDot11SvcHandle,
  _In_     PL2_NOTIFICATION_DATA pNotificationData
);
```


## -parameters




### -param hDot11SvcHandle [in, optional]

The handle used by the operating system to reference the wireless LAN (WLAN) adapter. This handle
     value was specified through a previous call to the
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


### -param pNotificationData [in]

A pointer to an
     <a href="https://docs.microsoft.com/windows/desktop/api/l2cmn/ns-l2cmn-_l2_notification_data">L2_NOTIFICATION_DATA</a> structure.



<div class="alert"><b>Note</b>  The IHV Extensions DLL must not pass a <b>NULL</b> value for this parameter.</div>



## -returns



If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in
     Winerror.h.




## -remarks



A service or application registers to receive the notification by calling the
    <b>WlanRegisterNotification</b> Auto Configuration Manager (ACM) function. For more information about this
    function, refer to the Microsoft Windows SDK documentation.

If the IHV Extensions DLL allocated memory for the notification data referenced by the
    <i>pNotificationData</i> parameter, the DLL can free the memory after the call to
    <b>Dot11ExtSendNotification</b> returns.




## -see-also

<a href="https://docs.microsoft.com/windows/desktop/api/l2cmn/ns-l2cmn-_l2_notification_data">L2_NOTIFICATION_DATA</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



 

 


