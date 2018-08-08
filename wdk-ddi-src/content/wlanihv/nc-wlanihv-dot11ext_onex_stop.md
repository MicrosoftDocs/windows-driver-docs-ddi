---
UID: NC:wlanihv.DOT11EXT_ONEX_STOP
title: DOT11EXT_ONEX_STOP
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extstoponex.htm
tech.root: netvista
ms.assetid: b4893698-47ae-4888-9dcd-0dbdf051266b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: DOT11EXT_ONEX_STOP, Dot11ExtStopOneX, Dot11ExtStopOneX callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_fcc1f11d-938e-431e-8327-42d34fedff04.xml, netvista.dot11extstoponex, wlanihv/Dot11ExtStopOneX
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	wlanihv.h
api_name:
-	Dot11ExtStopOneX
product:
- Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXT_ONEX_STOP callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The IHV Extensions DLL calls the
  <b>Dot11ExtStopOneX</b> function to cancel an 802.1X authentication operation with
  the access point (AP). The DLL initiated the authentication through a call to the
  <a href="..\wlanihv\nc-wlanihv-dot11ext_onex_start.md">Dot11ExtStartOneX</a> function.


## -prototype


````
DWORD WINAPI * Dot11ExtStopOneX(
  _In_opt_ HANDLE hDot11SvcHandle
);
````


## -parameters




### -param hDot11SvcHandle [in, optional]

The handle used by the operating system to reference the wireless LAN (WLAN) adapter. This handle
     value was specified through a previous call to the
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


## -returns



If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in
     Winerror.h.




## -remarks



When it calls the
    <a href="..\wlanihv\nc-wlanihv-dot11ext_onex_start.md">Dot11ExtStartOneX</a> function, the IHV
    Extensions DLL initiates an 802.1X authentication operation by using the 802.1X module of the Native
    802.11 framework. This allows the DLL to use the standard extensible authentication protocol (EAP)
    algorithms that are supported by the operating system.

Before the 802.1X authentication operation completes, the IHV Extensions DLL can call the
    <b>Dot11ExtStopOneX</b> function to cancel the operation.

When calling the
    <b>Dot11ExtStopOneX</b> function, the IHV Extensions DLL must follow these
    guidelines.

<ul>
<li>
<b>Dot11ExtStopOneX</b> can only be called while an 802.1X authentication
      operation is pending. The IHV Extensions DLL initiates the authentication with the AP by calling
      <a href="..\wlanihv\nc-wlanihv-dot11ext_onex_start.md">Dot11ExtStartOneX</a>. When the 802.1X
      authentication operation is completed, the operating system calls the
      <a href="..\wlanihv\nc-wlanihv-dot11extihv_onex_indicate_result.md">
      Dot11ExtIhvOneXIndicateResult</a> IHV Handler function.

</li>
<li>
After the IHV Extensions DLL calls
      <b>Dot11ExtStopOneX</b>, it must not call
      <a href="..\wlanihv\nc-wlanihv-dot11ext_process_onex_packet.md">Dot11ExtProcessOneXPacket</a> to
      forward 802.1X EAP over LAN (EAPOL) packets to the operating system. For more information about EAPOL
      packets, refer to Clause 7 of the IEEE 802.1X-2001 standard.

</li>
</ul>
For more information about using the 802.1X module for authentication, see
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/interface-to-the-native-802-11-802-1x-module">Interface to the Native
    802.11 802.1X Module</a>.




## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11ext_post_associate_completion.md">
   Dot11ExtPostAssociateCompletion</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_receive_packet.md">Dot11ExtIhvReceivePacket</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_process_onex_packet.md">Dot11ExtProcessOneXPacket</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_onex_indicate_result.md">
   Dot11ExtIhvOneXIndicateResult</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_onex_start.md">Dot11ExtStartOneX</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_post_associate.md">
   Dot11ExtIhvPerformPostAssociate</a>



 

 


