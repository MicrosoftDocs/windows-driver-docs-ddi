---
UID: NS:wlclient._DOT11_SECURITY_PACKET_HEADER
title: "_DOT11_SECURITY_PACKET_HEADER"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_security_packet_header.htm
tech.root: netvista
ms.assetid: 3a880137-58a6-4b89-8384-a92c37f289a2
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PDOT11_SECURITY_PACKET_HEADER, DOT11_SECURITY_PACKET_HEADER, DOT11_SECURITY_PACKET_HEADER structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_b694e370-23cc-4a3c-bb9f-deda406dd5c6.xml, PDOT11_SECURITY_PACKET_HEADER, PDOT11_SECURITY_PACKET_HEADER structure pointer [Network Drivers Starting with Windows Vista], _DOT11_SECURITY_PACKET_HEADER, netvista.dot11_security_packet_header, wlclient/DOT11_SECURITY_PACKET_HEADER, wlclient/PDOT11_SECURITY_PACKET_HEADER"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wlclient.h
req.include-header: Wlanihv.h
req.target-type: Windows
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
-	HeaderDef
api_location:
-	wlclient.h
api_name:
-	DOT11_SECURITY_PACKET_HEADER
product:
- Windows
targetos: Windows
req.typenames: DOT11_SECURITY_PACKET_HEADER, *PDOT11_SECURITY_PACKET_HEADER
req.product: Windows 10 or later.
---

# _DOT11_SECURITY_PACKET_HEADER structure


## -description


<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_SECURITY_PACKET_HEADER structure specifies security data used in a network packet
  header.


## -syntax


```cpp
typedef struct _DOT11_SECURITY_PACKET_HEADER {
  DOT11_MAC_ADDRESS PeerMac;
  USHORT            usEtherType;
  UCHAR             Data[1];
} DOT11_SECURITY_PACKET_HEADER, *PDOT11_SECURITY_PACKET_HEADER;
```


## -struct-fields




### -field PeerMac

A
     <a href="..\windot11\ns-windot11-_dot11_mac_address.md">DOT11_MAC_ADDRESS</a> type that defines the
     MAC address of the peer node.


### -field usEtherType

The value of the
     <a href="https://docs.microsoft.com/windows-hardware/drivers/network/ieee-ethertype-handling">IEEE EtherType</a> in big-endian byte
     order.


### -field Data

The contents of the security packet, excluding the 801.11 MAC header.


## -see-also

<a href="..\windot11\ns-windot11-_dot11_mac_address.md">DOT11_MAC_ADDRESS</a>



 

 


