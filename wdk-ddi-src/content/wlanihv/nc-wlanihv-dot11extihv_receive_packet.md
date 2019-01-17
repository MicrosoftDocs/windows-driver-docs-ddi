---
UID: NC:wlanihv.DOT11EXTIHV_RECEIVE_PACKET
title: DOT11EXTIHV_RECEIVE_PACKET
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvreceivepacket.htm
tech.root: netvista
ms.assetid: 4a08c6dc-61ac-421f-83b7-73f1f54aea71
ms.date: 02/16/2018
ms.keywords: DOT11EXTIHV_RECEIVE_PACKET, Dot11ExtIhvReceivePacket, Dot11ExtIhvReceivePacket callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_8f86438e-c311-425f-952f-08311bc3be2b.xml, netvista.dot11extihvreceivepacket, wlanihv/Dot11ExtIhvReceivePacket
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
-	Dot11ExtIhvReceivePacket
product:
- Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXTIHV_RECEIVE_PACKET callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The operating system calls the
  <i>Dot11ExtIhvReceivePacket</i> function to forward a packet, received by the wireless LAN (WLAN) adapter,
  to the IHV Extensions DLL for processing.


## -prototype


```cpp
DOT11EXTIHV_RECEIVE_PACKET Dot11ExtIhvReceivePacket;

DWORD APIENTRY Dot11ExtIhvReceivePacket(
  _In_opt_ HANDLE hIhvExtAdapter,
  _In_     DWORD  dwInBufferSize,
  _In_     LPVOID pvInBuffer
)
{ ... }
```


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
      <a href="..\wlanihv\nc-wlanihv-dot11ext_set_ethertype_handling.md">
      Dot11ExtSetEtherTypeHandling</a> function.

</li>
</ul>
The buffer pointed to by
    <i>pvPacket</i> should contain the following packet data, specified in network byte order:

<ul>
<li>
MAC address of destination (6 bytes), formatted according to the guidelines discussed in
      <a href="https://technet.microsoft.com/library/cc757419">802.11 MAC Header
      Management</a>


</li>
<li>
IEEE EtherType (2 bytes)

</li>
<li>
Payload

</li>
</ul>



## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11ext_set_ethertype_handling.md">Dot11ExtSetEtherTypeHandling</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



 

 


