---
UID: NC:wlanihv.DOT11EXTIHV_RECEIVE_INDICATION
title: DOT11EXTIHV_RECEIVE_INDICATION (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvreceiveindication.htm
tech.root: netvista
ms.assetid: b4d5c33e-563d-459c-90da-a2912c82d1cd
ms.date: 02/16/2018
keywords: ["DOT11EXTIHV_RECEIVE_INDICATION callback"]
ms.keywords: DOT11EXTIHV_RECEIVE_INDICATION, Dot11ExtIhvReceiveIndication, Dot11ExtIhvReceiveIndication callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_f3bf018e-2849-4abc-af5b-4edb3438339f.xml, netvista.dot11extihvreceiveindication, wlanihv/Dot11ExtIhvReceiveIndication
f1_keywords:
 - "wlanihv/Dot11ExtIhvReceiveIndication"
req.header: wlanihv.h
req.include-header: Wlanihv.h
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
- Dot11ExtIhvReceiveIndication
product:
- Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXTIHV_RECEIVE_INDICATION callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The operating system calls the
  <i>Dot11ExtIhvReceiveIndication</i> function to issue an IHV-specific indication to the IHV Extensions DLL
  from the wireless LAN (WLAN) adapter.


## -prototype


```cpp
DOT11EXTIHV_RECEIVE_INDICATION Dot11ExtIhvReceiveIndication;

DWORD APIENTRY Dot11ExtIhvReceiveIndication(
  _In_opt_ HANDLE                       hIhvExtAdapter,
  _In_     DOT11EXT_IHV_INDICATION_TYPE indicationType,
  _In_     ULONG                        uBufferLength,
  _In_opt_ LPVOID                       pvBuffer
)
{ ... }
```


## -parameters




### -param hIhvExtAdapter [in, optional]

The handle used by the IHV Extensions DLL to reference the WLAN adapter. This handle value was
     specified through a previous call to the
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


### -param indicationType [in]

The
     <a href="..\wlanihv\ne-wlanihv-_dot11ext_ihv_indication_type.md">
     DOT11EXT_IHV_INDICATION_TYPE</a> indication type.


### -param uBufferLength [in]

The length, in bytes, of the data within the buffer that is referenced by the
     <i>pvBuffer</i> parameter.


### -param pvBuffer [in, optional]

The pointer to a buffer, allocated by the operating system, which contains the notification data.
     The IHV is responsible for defining the format of the notification data.


## -returns



If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in
     Winerror.h.




## -remarks



When the Native 802.11 miniport driver, which manages the WLAN adapter, makes an
    <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-media-specific-indication">
    NDIS_STATUS_MEDIA_SPECIFIC_INDICATION</a> indication, the operating system forwards the notification
    data to the IHV Extensions DLL by calling the
    <i>Dot11ExtIhvReceiveIndication</i> function.




## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/ndis-status-media-specific-indication">
   NDIS_STATUS_MEDIA_SPECIFIC_INDICATION</a>



<a href="..\wlanihv\ne-wlanihv-_dot11ext_ihv_indication_type.md">DOT11EXT_IHV_INDICATION_TYPE</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



 

 


