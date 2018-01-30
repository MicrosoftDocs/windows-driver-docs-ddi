---
UID: NC:wlanihv.DOT11EXTIHV_RECEIVE_PACKET
title: DOT11EXTIHV_RECEIVE_PACKET
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvreceivepacket.htm
old-project: netvista
ms.assetid: 4a08c6dc-61ac-421f-83b7-73f1f54aea71
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.dot11extihvreceivepacket, Dot11ExtIhvReceivePacket callback function [Network Drivers Starting with Windows Vista], Dot11ExtIhvReceivePacket, DOT11EXTIHV_RECEIVE_PACKET, DOT11EXTIHV_RECEIVE_PACKET, wlanihv/Dot11ExtIhvReceivePacket, Native_802.11_IHV_Ext_8f86438e-c311-425f-952f-08311bc3be2b.xml
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
-	Dot11ExtIhvReceivePacket
product: Windows
targetos: Windows
req.typenames: "*LPDRIVER_INFO_8W, DRIVER_INFO_8W, *PDRIVER_INFO_8W"
req.product: Windows 10 or later.
---

# DOT11EXTIHV_RECEIVE_PACKET callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The operating system calls the 
  <i>Dot11ExtIhvReceivePacket</i> function to forward a packet, received by the wireless LAN (WLAN) adapter,
  to the IHV Extensions DLL for processing.


## -prototype


````
DOT11EXTIHV_RECEIVE_PACKET Dot11ExtIhvReceivePacket;

DWORD APIENTRY Dot11ExtIhvReceivePacket(
  _In_opt_ HANDLE hIhvExtAdapter,
  _In_     DWORD  dwInBufferSize,
  _In_     LPVOID pvInBuffer
)
{ ... }
````


## -parameters




### -param hIhvExtAdapter [in, optional]

The handle used by the IHV Extensions DLL to reference the WLAN adapter. This handle value was
     specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


### -param dwInBufferSize [in]

The length, in bytes, of the received packet referenced by the 
     <i>pvInBuffer</i> parameter.


### -param pvInBuffer [in]

A pointer to a buffer, allocated by the operating system, which contains the packet data, as
     described in the Remarks section.


## -returns


If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.



## -remarks


The operating system calls the 
    <i>Dot11ExtIhvReceivePacket</i> function when the following occur:
<ul>
<li>
The WLAN adapter receives a packet and the Native 802.11 miniport driver, which manages the adapter,
      indicates the packet to the operating system.

</li>
<li>
The packet's IEEE EtherType matches an entry in the list of EtherTypes specified by the IHV
      Extensions DLL through a call to the 
      <mshelp:link keywords="netvista.dot11extsetethertypehandling" tabindex="0"><b>
      Dot11ExtSetEtherTypeHandling</b></mshelp:link> function.

</li>
</ul>The buffer pointed to by 
    <i>pvPacket</i> should contain the following packet data, specified in network byte order:
<ul>
<li>
MAC address of destination (6 bytes), formatted according to the guidelines discussed in 
      <mshelp:link keywords="netvista.802_11_mac_header_management" tabindex="0">802.11 MAC Header
      Management</mshelp:link>


</li>
<li>
IEEE EtherType (2 bytes)

</li>
<li>
Payload

</li>
</ul>


## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>

<a href="..\wlanihv\nc-wlanihv-dot11ext_set_ethertype_handling.md">Dot11ExtSetEtherTypeHandling</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXTIHV_RECEIVE_PACKET callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

