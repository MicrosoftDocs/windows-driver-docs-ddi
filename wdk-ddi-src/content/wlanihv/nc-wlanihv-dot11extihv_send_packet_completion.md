---
UID: NC:wlanihv.DOT11EXTIHV_SEND_PACKET_COMPLETION
title: DOT11EXTIHV_SEND_PACKET_COMPLETION
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extihvsendpacketcompletion.htm
old-project: netvista
ms.assetid: 117a9806-95a0-4f2f-8280-fec035df2811
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
req.alt-api: Dot11ExtIhvSendPacketCompletion
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

# DOT11EXTIHV_SEND_PACKET_COMPLETION callback



## -description

## -prototype

````
DOT11EXTIHV_SEND_PACKET_COMPLETION Dot11ExtIhvSendPacketCompletion;

DWORD APIENTRY Dot11ExtIhvSendPacketCompletion(
  _In_opt_ HANDLE hSendCompletion
)
{ ... }
````


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
<dl>
<dt>
<a href="..\wlanihv\nc-wlanihv-dot11ext_send_packet.md">Dot11ExtSendPacket</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXTIHV_SEND_PACKET_COMPLETION callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

