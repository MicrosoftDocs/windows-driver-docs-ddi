---
UID: NC:wlanihv.DOT11EXT_SEND_PACKET
title: DOT11EXT_SEND_PACKET
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extsendpacket.htm
old-project: netvista
ms.assetid: 0672eed0-4824-464b-9f4e-93862f27d586
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
req.alt-api: Dot11ExtSendPacket
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

# DOT11EXT_SEND_PACKET callback



## -description

## -prototype

````
DWORD WINAPI * Dot11ExtSendPacket(
  _In_opt_ HANDLE hDot11SvcHandle,
  _In_     ULONG  uPacketLen,
  _In_     LPVOID pvPacket,
  _In_opt_ HANDLE hSendCompletion
);
````


## -parameters

### -param hDot11SvcHandle [in, optional]

The handle used by the operating system to reference the WLAN adapter. This handle value was
     specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


### -param uPacketLen [in]

The length, in bytes, of the caller-allocated buffer referenced by the 
     <i>pvPacket</i> parameter.


### -param pvPacket [in]

A pointer to a caller-allocated buffer that contains the data to be transmitted, as described in
     the Remarks section.


### -param hSendCompletion [in, optional]

A handle value that uniquely identifies the send packet. 
     

When the WLAN adapter completes the send operation, the operating system notifies the IHV Extensions
     DLL through a call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_send_packet_completion.md">
     Dot11ExtIhvSendPacketCompletion</a> IHV Handler function. When making this call, the operating system
     passes the handle value of the packet through the 
     <i>hSendCompletion</i> parameter.


## -returns
If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in 
     Winerror.h.


## -remarks
The IHV Extensions DLL must follow these guidelines when calling the 
    <b>Dot11ExtSendPacket</b> function.

The packet sent through a call of the 
      <b>Dot11ExtSendPacket</b> function will complete asynchronously. The IHV
      Extensions DLL must not free the memory referenced by the 
      <i>pvPacket</i> parameter until the 
      <a href="..\wlanihv\nc-wlanihv-dot11extihv_send_packet_completion.md">
      Dot11ExtIhvSendPacketCompletion</a> IHV Handler function is called with the same handle value as the 
      <i>hSendCompletion</i> parameter.

The IHV Extensions DLL must set the 
      <i>hSendCompletion</i> parameter to a value that uniquely identifies the packet data that is referenced
      by the 
      <i>pvPacket</i> parameter.

For more information about the IHV Handler functions, see 
    <a href="netvista.native_802_11_ihv_handler_functions">Native 802.11 IHV Handler
    Functions</a>.

The buffer pointed to by 
    <i>pvPacket</i> should contain the following packet data, specified in network byte order:

MAC address of destination (6 bytes), formatted according to the guidelines discussed in 
      <a href="netvista.802_11_mac_header_management">802.11 MAC Header
      Management</a>


IEEE EtherType (2 bytes)

Payload

This packet data is passed to the miniport driver.


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/20bf0527-35ef-4c61-92d8-042391cb0203">802.11 MAC Header Management</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>
</dt>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11extihv_send_packet_completion.md">
   Dot11ExtIhvSendPacketCompletion</a>
</dt>
<dt>
<a href="netvista.native_802_11_ihv_handler_functions">Native 802.11 IHV Handler
   Functions</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_SEND_PACKET callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

