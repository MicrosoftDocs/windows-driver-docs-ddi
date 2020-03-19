---
UID: NC:wlanihv.DOT11EXTIHV_SEND_PACKET_COMPLETION
title: DOT11EXTIHV_SEND_PACKET_COMPLETION (wlanihv.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvsendpacketcompletion.htm
tech.root: netvista
ms.assetid: 117a9806-95a0-4f2f-8280-fec035df2811
ms.date: 02/16/2018
keywords: ["DOT11EXTIHV_SEND_PACKET_COMPLETION callback"]
ms.keywords: DOT11EXTIHV_SEND_PACKET_COMPLETION, Dot11ExtIhvSendPacketCompletion, Dot11ExtIhvSendPacketCompletion callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_c0d3f967-28a9-4242-9a4b-2faed66ae5b1.xml, netvista.dot11extihvsendpacketcompletion, wlanihv/Dot11ExtIhvSendPacketCompletion
f1_keywords:
 - "wlanihv/Dot11ExtIhvSendPacketCompletion"
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
- Dot11ExtIhvSendPacketCompletion
product:
- Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXTIHV_SEND_PACKET_COMPLETION callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://docs.microsoft.com/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://docs.microsoft.com/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The operating system calls the
  <i>Dot11ExtIhvSendPacketCompletion</i> function to complete the send of a packet. The IHV Extensions DLL
  initiated the packet send by calling the
  <a href="..\wlanihv\nc-wlanihv-dot11ext_send_packet.md">Dot11ExtSendPacket</a> function.


## -prototype


```cpp
DOT11EXTIHV_SEND_PACKET_COMPLETION Dot11ExtIhvSendPacketCompletion;

DWORD APIENTRY Dot11ExtIhvSendPacketCompletion(
  _In_opt_ HANDLE hSendCompletion
)
{ ... }
```


## -parameters




### -param hSendCompletion [in, optional]

The handle value that the IHV Extensions DLL used to identify the packet when it called the
     <a href="..\wlanihv\nc-wlanihv-dot11ext_send_packet.md">Dot11ExtSendPacket</a> function.


## -returns



If the call succeeds, the function returns ERROR_SUCCESS. Otherwise, it returns an error code
     defined in
     Winerror.h.




## -remarks



When the operating system calls the
    <i>Dot11ExtIhvSendPacketCompletion</i> function, the IHV Extensions DLL can free the resources it
    allocated for the packet send.




## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11ext_send_packet.md">Dot11ExtSendPacket</a>



 

 


