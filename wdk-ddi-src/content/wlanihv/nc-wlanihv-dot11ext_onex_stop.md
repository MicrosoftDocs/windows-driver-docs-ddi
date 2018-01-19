---
UID: NC:wlanihv.DOT11EXT_ONEX_STOP
title: DOT11EXT_ONEX_STOP
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extstoponex.htm
old-project: netvista
ms.assetid: b4893698-47ae-4888-9dcd-0dbdf051266b
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
req.alt-api: Dot11ExtStopOneX
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

# DOT11EXT_ONEX_STOP callback



## -description

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

<b>Dot11ExtStopOneX</b> can only be called while an 802.1X authentication
      operation is pending. The IHV Extensions DLL initiates the authentication with the AP by calling 
      <a href="..\wlanihv\nc-wlanihv-dot11ext_onex_start.md">Dot11ExtStartOneX</a>. When the 802.1X
      authentication operation is completed, the operating system calls the 
      <a href="..\wlanihv\nc-wlanihv-dot11extihv_onex_indicate_result.md">
      Dot11ExtIhvOneXIndicateResult</a> IHV Handler function.

After the IHV Extensions DLL calls 
      <b>Dot11ExtStopOneX</b>, it must not call 
      <a href="..\wlanihv\nc-wlanihv-dot11ext_process_onex_packet.md">Dot11ExtProcessOneXPacket</a> to
      forward 802.1X EAP over LAN (EAPOL) packets to the operating system. For more information about EAPOL
      packets, refer to Clause 7 of the IEEE 802.1X-2001 standard.

For more information about using the 802.1X module for authentication, see 
    <a href="netvista.interface_to_the_native_802_11_802_1x_module">Interface to the Native
    802.11 802.1X Module</a>.


## -see-also
<dl>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_onex_indicate_result.md">
   Dot11ExtIhvOneXIndicateResult</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_perform_post_associate.md">
   Dot11ExtIhvPerformPostAssociate</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_receive_packet.md">Dot11ExtIhvReceivePacket</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11ext_onex_start.md">Dot11ExtStartOneX</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11ext_post_associate_completion.md">
   Dot11ExtPostAssociateCompletion</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11ext_process_onex_packet.md">Dot11ExtProcessOneXPacket</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_ONEX_STOP callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

