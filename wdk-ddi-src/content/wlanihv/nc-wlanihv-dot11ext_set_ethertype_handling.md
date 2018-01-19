---
UID: NC:wlanihv.DOT11EXT_SET_ETHERTYPE_HANDLING
title: DOT11EXT_SET_ETHERTYPE_HANDLING
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extsetethertypehandling.htm
old-project: netvista
ms.assetid: 0681519e-022a-487c-ae5e-39a293b060ec
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _DRIVER_INFO_8W, *LPDRIVER_INFO_8W, *PDRIVER_INFO_8W, DRIVER_INFO_8W, DRIVER_INFO_8
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
req.alt-api: Dot11ExtSetEtherTypeHandling
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

# DOT11EXT_SET_ETHERTYPE_HANDLING callback



## -description

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


### -param pusRegistration [in, optional]

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

The IHV Extensions DLL can call 
      <b>Dot11ExtSetEtherTypeHandling</b> from within the calls to either the 
      <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> or 
      <a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
      Dot11ExtIhvPerformPreAssociate</a> IHV Handler functions.

The IHV Extensions DLL must not call 
      <b>Dot11ExtSetEtherTypeHandling</b> after successfully completing the
      pre-association operation through a call to 
      <a href="..\wlanihv\nc-wlanihv-dot11ext_pre_associate_completion.md">
      Dot11ExtPreAssociateCompletion</a>.

The operating system defaults to an empty list of privacy exemptions and EtherType registrations prior
    to the call of the 
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
    Handler function.


## -see-also
<dl>
<dt>
<a href="..\windot11\ns-windot11-dot11_privacy_exemption.md">DOT11_PRIVACY_EXEMPTION</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_pre_associate.md">
   Dot11ExtIhvPerformPreAssociate</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_receive_packet.md">Dot11ExtIhvReceivePacket</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11ext_pre_associate_completion.md">
   Dot11ExtPreAssociateCompletion</a>
</dt>
<dt>
<a href="netvista.native_802_11_ihv_handler_functions">Native 802.11 IHV Handler
   Functions</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_SET_ETHERTYPE_HANDLING callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

