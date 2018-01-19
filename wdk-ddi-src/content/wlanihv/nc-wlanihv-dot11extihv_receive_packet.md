---
UID: NC:wlanihv.DOT11EXTIHV_RECEIVE_PACKET
title: DOT11EXTIHV_RECEIVE_PACKET
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvreceivepacket.htm
old-project: netvista
ms.assetid: 4a08c6dc-61ac-421f-83b7-73f1f54aea71
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
req.alt-api: Dot11ExtIhvReceivePacket
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

# DOT11EXTIHV_RECEIVE_PACKET callback



## -description

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

The WLAN adapter receives a packet and the Native 802.11 miniport driver, which manages the adapter,
      indicates the packet to the operating system.

The packet's IEEE EtherType matches an entry in the list of EtherTypes specified by the IHV
      Extensions DLL through a call to the 
      <a href="..\wlanihv\nc-wlanihv-dot11ext_set_ethertype_handling.md">
      Dot11ExtSetEtherTypeHandling</a> function.

The buffer pointed to by 
    <i>pvPacket</i> should contain the following packet data, specified in network byte order:

MAC address of destination (6 bytes), formatted according to the guidelines discussed in 
      <a href="netvista.802_11_mac_header_management">802.11 MAC Header
      Management</a>


IEEE EtherType (2 bytes)

Payload


## -see-also
<dl>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11ext_set_ethertype_handling.md">Dot11ExtSetEtherTypeHandling</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXTIHV_RECEIVE_PACKET callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

