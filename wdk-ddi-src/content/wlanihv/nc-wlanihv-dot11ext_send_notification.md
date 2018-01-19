---
UID: NC:wlanihv.DOT11EXT_SEND_NOTIFICATION
title: DOT11EXT_SEND_NOTIFICATION
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extsendnotification.htm
old-project: netvista
ms.assetid: 8191b375-537e-44df-920e-077c77ed2354
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DRIVER_INFO_8W, *LPDRIVER_INFO_8W, *PDRIVER_INFO_8W, DRIVER_INFO_8W, DRIVER_INFO_8
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
req.alt-api: Dot11ExtSendNotification
req.alt-loc: wlanihv.h
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
req.typenames: *LPDRIVER_INFO_8W, *PDRIVER_INFO_8W, DRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXT_SEND_NOTIFICATION callback



## -description

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
<dl>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557044">L2_NOTIFICATION_DATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_SEND_NOTIFICATION callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

