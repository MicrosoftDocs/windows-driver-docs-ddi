---
UID: NC:wlanihv.DOT11EXT_SEND_NOTIFICATION
title: DOT11EXT_SEND_NOTIFICATION
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extsendnotification.htm
old-project: netvista
ms.assetid: 8191b375-537e-44df-920e-077c77ed2354
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.dot11extsendnotification, Dot11ExtSendNotification callback function [Network Drivers Starting with Windows Vista], Dot11ExtSendNotification, DOT11EXT_SEND_NOTIFICATION, DOT11EXT_SEND_NOTIFICATION, wlanihv/Dot11ExtSendNotification, Native_802.11_IHV_Ext_163e65f4-108a-4d10-bcf7-b487bd3cc0c9.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	wlanihv.h
apiname:
-	Dot11ExtSendNotification
product: Windows
targetos: Windows
req.typenames: "*LPDRIVER_INFO_8W, DRIVER_INFO_8W, *PDRIVER_INFO_8W"
req.product: Windows 10 or later.
---

# DOT11EXT_SEND_NOTIFICATION callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The IHV Extensions DLL calls the 
  <b>Dot11ExtSendNotification</b> function to send notifications to any service or
  application that has registered for the notification.


## -prototype


````
DWORD WINAPI * Dot11ExtSendNotification(
  _In_opt_ HANDLE                hDot11SvcHandle,
  _In_     PL2_NOTIFICATION_DATA pNotificationData
);
````


## -parameters




### -param hDot11SvcHandle [in, optional]

The handle used by the operating system to reference the wireless LAN (WLAN) adapter. This handle
     value was specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


### -param pNotificationData [in]

A pointer to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff557044">L2_NOTIFICATION_DATA</a> structure.
     


<div class="alert"><b>Note</b>  The IHV Extensions DLL must not pass a <b>NULL</b> value for this parameter.</div>
<div> </div>



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

<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557044">L2_NOTIFICATION_DATA</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_SEND_NOTIFICATION callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

