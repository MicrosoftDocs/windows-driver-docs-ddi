---
UID: NS:wlclient._DOT11_SECURITY_PACKET_HEADER
title: _DOT11_SECURITY_PACKET_HEADER (wlclient.h)
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_security_packet_header.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_SECURITY_PACKET_HEADER structure"]
ms.keywords: "*PDOT11_SECURITY_PACKET_HEADER, DOT11_SECURITY_PACKET_HEADER, DOT11_SECURITY_PACKET_HEADER structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_b694e370-23cc-4a3c-bb9f-deda406dd5c6.xml, PDOT11_SECURITY_PACKET_HEADER, PDOT11_SECURITY_PACKET_HEADER structure pointer [Network Drivers Starting with Windows Vista], _DOT11_SECURITY_PACKET_HEADER, netvista.dot11_security_packet_header, wlclient/DOT11_SECURITY_PACKET_HEADER, wlclient/PDOT11_SECURITY_PACKET_HEADER"
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
targetos: Windows
req.typenames: DOT11_SECURITY_PACKET_HEADER, *PDOT11_SECURITY_PACKET_HEADER
req.product: Windows 10 or later.
f1_keywords:
 - _DOT11_SECURITY_PACKET_HEADER
 - wlclient/_DOT11_SECURITY_PACKET_HEADER
 - PDOT11_SECURITY_PACKET_HEADER
 - wlclient/PDOT11_SECURITY_PACKET_HEADER
 - DOT11_SECURITY_PACKET_HEADER
 - wlclient/DOT11_SECURITY_PACKET_HEADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - wlclient.h
api_name:
 - _DOT11_SECURITY_PACKET_HEADER
 - PDOT11_SECURITY_PACKET_HEADER
 - DOT11_SECURITY_PACKET_HEADER
---

# _DOT11_SECURITY_PACKET_HEADER structure


## -description

<div class="alert"><b>Important</b>  The <a href="/previous-versions/windows/hardware/wireless/ff560689(v=vs.85)">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="/windows-hardware/drivers/network/wifi-universal-driver-model">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_SECURITY_PACKET_HEADER structure specifies security data used in a network packet
  header.

## -struct-fields

### -field PeerMac

A
     <a href="..\windot11\ns-windot11-_dot11_mac_address.md">DOT11_MAC_ADDRESS</a> type that defines the
     MAC address of the peer node.

### -field usEtherType

The value of the
     <a href="/windows-hardware/drivers/network/ieee-ethertype-handling">IEEE EtherType</a> in big-endian byte
     order.

### -field Data

The contents of the security packet, excluding the 801.11 MAC header.

## -syntax

```cpp
typedef struct _DOT11_SECURITY_PACKET_HEADER {
  DOT11_MAC_ADDRESS PeerMac;
  USHORT            usEtherType;
  UCHAR             Data[1];
} DOT11_SECURITY_PACKET_HEADER, *PDOT11_SECURITY_PACKET_HEADER;
```

## -see-also

<a href="..\windot11\ns-windot11-_dot11_mac_address.md">DOT11_MAC_ADDRESS</a>

