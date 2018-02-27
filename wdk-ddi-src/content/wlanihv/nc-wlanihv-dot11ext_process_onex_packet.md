---
UID: NC:wlanihv.DOT11EXT_PROCESS_ONEX_PACKET
title: DOT11EXT_PROCESS_ONEX_PACKET
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11extprocessonexpacket.htm
old-project: netvista
ms.assetid: 796c2976-b7b1-49ea-bf23-c018efd228ee
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: DOT11EXT_PROCESS_ONEX_PACKET, Dot11ExtProcessOneXPacket, Dot11ExtProcessOneXPacket callback function [Network Drivers Starting with Windows Vista], Native_802.11_IHV_Ext_261bf893-01bf-45d2-96da-b11745a2ae56.xml, netvista.dot11extprocessonexpacket, wlanihv/Dot11ExtProcessOneXPacket
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
-	Dot11ExtProcessOneXPacket
product: Windows
targetos: Windows
req.typenames: DRIVER_INFO_8W, *PDRIVER_INFO_8W, *LPDRIVER_INFO_8W
req.product: Windows 10 or later.
---

# DOT11EXT_PROCESS_ONEX_PACKET callback


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The IHV Extensions DLL calls the 
  <b>Dot11ExtProcessOneXPacket</b> function to forward EAP over LAN (EAPOL) packets
  to the operating system for processing during an 802.1X authentication operation with the access point
  (AP).


## -prototype


````
DWORD WINAPI * Dot11ExtProcessOneXPacket(
  _In_opt_ HANDLE hDot11SvcHandle,
  _In_     DWORD  dwInPacketSize,
  _In_     LPVOID pvInPacket
);
````


## -parameters




### -param hDot11SvcHandle [in, optional]

The handle used by the operating system to reference the wireless LAN (WLAN) adapter. This handle
     value was specified through a previous call to the 
     <a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a> IHV
     Handler function.


### -param dwInPacketSize [in]

The length, in bytes, of the packet data within the buffer that is referenced by the 
     <i>pvInPacket</i> parameter.


### -param pvInPacket [in]

The EAPOL packet received from the AP. The 
     <i>pvInPacket</i> parameter must reference the EAPOL packet starting from the packet type field in the
     EAPOL protocol data unit (PDU). For more information about the EAPOL packet type field, refer to Clause
     7.5.4 in the IEEE 802.1X-2001 standard.


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

While the 802.1X authentication operation is pending, the IHV Extensions DLL forwards received EAP
    over LAN (EAPOL) packets to the operating system through a call to the 
    <b>Dot11ExtProcessOneXPacket</b> function. The IHV Extensions DLL receives these
    packets through the 
    <a href="..\wlanihv\nc-wlanihv-dot11extihv_receive_packet.md">Dot11ExtIhvReceivePacket</a> IHV
    Handler function.

<div class="alert"><b>Note</b>  The IHV Extensions DLL is responsible for processing EAPOL-Key packets and must not
    forward these to the operating system.</div>
<div> </div>
For more information about EAPOL packets, refer to Clause 7 of the IEEE 802.1X-2001 standard.

For more information about using the 802.1X module for authentication, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/interface-to-the-native-802-11-802-1x-module">Interface to the Native
    802.11 802.1X Module</a>





## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11ext_onex_stop.md">Dot11ExtStopOneX</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_receive_packet.md">Dot11ExtIhvReceivePacket</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_init_adapter.md">Dot11ExtIhvInitAdapter</a>



<a href="..\wlanihv\nc-wlanihv-dot11ext_onex_start.md">Dot11ExtStartOneX</a>



<a href="..\wlanihv\nc-wlanihv-dot11extihv_onex_indicate_result.md">
   Dot11ExtIhvOneXIndicateResult</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11EXT_PROCESS_ONEX_PACKET callback function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

