---
UID: NC:wlanihv.DOT11EXTIHV_RECEIVE_INDICATION
title: DOT11EXTIHV_RECEIVE_INDICATION
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvreceiveindication.htm
old-project: netvista
ms.assetid: b4d5c33e-563d-459c-90da-a2912c82d1cd
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.dot11extihvreceiveindication, Dot11ExtIhvReceiveIndication callback function [Network Drivers Starting with Windows Vista], Dot11ExtIhvReceiveIndication, DOT11EXTIHV_RECEIVE_INDICATION, DOT11EXTIHV_RECEIVE_INDICATION, wlanihv/Dot11ExtIhvReceiveIndication, Native_802.11_IHV_Ext_f3bf018e-2849-4abc-af5b-4edb3438339f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	UserDefined
apilocation: 
-	wlanihv.h
apiname: 
-	Dot11ExtIhvReceiveIndication
product: Windows
targetos: Windows
req.typenames: *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W, DRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXTIHV_RECEIVE_INDICATION callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The operating system calls the 
  <i>Dot11ExtIhvReceiveIndication</i> function to issue an IHV-specific indication to the IHV Extensions DLL
  from the wireless LAN (WLAN) adapter.


## -prototype


````
DOT11EXTIHV_RECEIVE_INDICATION Dot11ExtIhvReceiveIndication;

DWORD APIENTRY Dot11ExtIhvReceiveIndication(
  _In_opt_ HANDLE                       hIhvExtAdapter,
  _In_     DOT11EXT_IHV_INDICATION_TYPE indicationType,
  _In_     ULONG                        uBufferLength,
  _In_opt_ LPVOID                       pvBuffer
)
{ ... }
````


## -parameters




### -param hIhvExtAdapter [in, optional]

The handle used by the IHV Extensions DLL to reference the WLAN adapter. This handle value was
     specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


### -param indicationType [in]

The 
     <mshelp:link keywords="netvista.dot11ext_ihv_indication_type" tabindex="0"><b>
     DOT11EXT_IHV_INDICATION_TYPE</b></mshelp:link> indication type.


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
    <mshelp:link keywords="netvista.ndis_status_media_specific_indication" tabindex="0"><b>
    NDIS_STATUS_MEDIA_SPECIFIC_INDICATION</b></mshelp:link> indication, the operating system forwards the notification
    data to the IHV Extensions DLL by calling the 
    <i>Dot11ExtIhvReceiveIndication</i> function.



## -see-also

<mshelp:link keywords="netvista.ndis_status_media_specific_indication" tabindex="0"><b>
   NDIS_STATUS_MEDIA_SPECIFIC_INDICATION</b></mshelp:link>

<a href="..\wlanihv\ne-wlanihv-_dot11ext_ihv_indication_type.md">DOT11EXT_IHV_INDICATION_TYPE</a>

<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXTIHV_RECEIVE_INDICATION callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

