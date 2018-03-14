---
UID: NC:wlanihv.DOT11EXT_SET_ETHERTYPE_HANDLING
title: DOT11EXT_SET_ETHERTYPE_HANDLING
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extsetethertypehandling.htm
old-project: netvista
ms.assetid: 0681519e-022a-487c-ae5e-39a293b060ec
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: DOT11EXT_SET_ETHERTYPE_HANDLING, Dot11ExtSetEtherTypeHandling, Dot11ExtSetEtherTypeHandling callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_6265fb16-690c-4ada-a79d-fa39760a63d2.xml, netvista.dot11extsetethertypehandling, wlanihv/Dot11ExtSetEtherTypeHandling
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
-	Dot11ExtSetEtherTypeHandling
product: Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXT_SET_ETHERTYPE_HANDLING callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The IHV Extensions DLL calls the 
  <b>Dot11ExtSetEtherTypeHandling</b> function to do the following:
  
<ul>
<li>
Configure the wireless LAN (WLAN) adapter with a list of packet decryption exemptions. Each exemption
    is applied based on the IEEE EtherType of the received packet.

</li>
<li>
Register with the operating system for the EtherTypes of received packets that will be forwarded to
    IHV Extensions DLL through calls to the 
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_receive_packet.md">Dot11ExtIhvReceivePacket</a> IHV
    Handler function.

</li>
</ul>

## -prototype


````
DWORD WINAPI * Dot11ExtSetEtherTypeHandling(
  _In_opt_ HANDLE                   hDot11SvcHandle,
  _In_     ULONG                    uMaxBackLog,
  _In_     ULONG                    uNumOfExemption,
  _In_opt_ PDOT11_PRIVACY_EXEMPTION pExemption,
  _In_     ULONG                    uNumOfRegistration,
  _In_opt_ USHORT                   *pusRegistration
);
````


## -parameters




### -param hDot11SvcHandle [in, optional]

The handle used by the operating system to reference the WLAN adapter. This handle value was
     specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


### -param uMaxBackLog [in]

The maximum number of received packets that the operating system queues if the IHV Extensions DLL
     has not returned from a call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_receive_packet.md">Dot11ExtIhvReceivePacket</a> IHV
     Handler function. When 
     <i>uMaxBackLog</i> is reached, the operating system discards the oldest packet in the queue.


### -param uNumOfExemption [in]

The number of entries within the privacy exemptions array referenced by the 
     <i>pExemption</i> parameter. A value of zero disables privacy exemptions on the WLAN adapter.


### -param pExemption [in, optional]

A pointer to an array of privacy exemptions. Each entry in the array is formatted as a 
     <a href="..\windot11\ns-windot11-dot11_privacy_exemption.md">
     DOT11_PRIVACY_EXEMPTION</a> structure.


### -param uNumOfRegistration [in]

Number of entries within the IEEE EtherType registrations array referenced by the 
     <i>pusRegistration</i> parameter. A value of zero disables the ability of the IHV Extensions DLL to
     receive any packets through calls to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_receive_packet.md">Dot11ExtIhvReceivePacket</a> IHV
     Handler function.


### -param *pusRegistration [in, optional]

A pointer to an array of IEEE EtherType registrations. Each entry has the EtherType value in
     big-endian format.


## -returns



If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.




## -remarks



When calling the 
    <b>Dot11ExtSetEtherTypeHandling</b> function, the IHV Extensions DLL must follow
    these guidelines:

<ul>
<li>
The IHV Extensions DLL can call 
      <b>Dot11ExtSetEtherTypeHandling</b> from within the calls to either the 
      <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> or 
      <a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
      Dot11ExtIhvPerformPreAssociate</a> IHV Handler functions.

</li>
<li>
The IHV Extensions DLL must not call 
      <b>Dot11ExtSetEtherTypeHandling</b> after successfully completing the
      pre-association operation through a call to 
      <a href="..\wlanihv\nc-wlanihv-dot11ext_pre_associate_completion.md">
      Dot11ExtPreAssociateCompletion</a>.

</li>
</ul>
The operating system defaults to an empty list of privacy exemptions and EtherType registrations prior
    to the call of the 
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
    Handler function.




## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11extihv_receive_packet.md">Dot11ExtIhvReceivePacket</a>



<a href="..\windot11\ns-windot11-dot11_privacy_exemption.md">DOT11_PRIVACY_EXEMPTION</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_pre_associate_completion.md">
   Dot11ExtPreAssociateCompletion</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/native-802-11-ihv-handler-functions">Native 802.11 IHV Handler
   Functions</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
   Dot11ExtIhvPerformPreAssociate</a>



 

 


